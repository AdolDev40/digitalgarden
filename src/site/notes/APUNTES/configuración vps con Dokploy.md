---
{"dg-publish":true,"permalink":"/apuntes/configuracion-vps-con-dokploy/","tags":["referencias","web/documentación"]}
---


# Guía Completa: Configuración VPS con Dokploy

## 🖥️ Información del Servidor

- Proveedor: DigitalOcean (o tu proveedor de preferencia)
- IP del Servidor: [IP_DEL_SERVIDOR]
- Sistema Operativo: Ubuntu 22.04 LTS o superior
- Dominio Principal: tu-dominio.com
- Subdominio Dokploy: dokploy.tu-dominio.com

## 🚀 Configuración Inicial del VPS

### Paso 1: Actualizar el Sistema

**Conecta por SSH a tu VPS y ejecuta:**

```
sudo apt update && sudo apt upgrade -y
```

**¿Por qué es importante?**

- Actualiza la lista de paquetes disponibles.
- Instala parches de seguridad críticos.
- Previene vulnerabilidades conocidas.

### Paso 2: Configurar el Firewall (UFW)

**El firewall protege tu servidor bloqueando tráfico no autorizado.**

```
# Permitir SSH (puerto 22) - NUNCA bloquees esto o perderás acceso
sudo ufw allow 22/tcp

# Permitir HTTP (puerto 80) - Necesario para validación SSL y acceso web
sudo ufw allow 80/tcp

# Permitir HTTPS (puerto 443) - Tráfico web cifrado
sudo ufw allow 443/tcp

# Permitir Puerto de Instalación (Opcional, usualmente 3000 para setup inicial)
sudo ufw allow 3000/tcp

# Activar el firewall
sudo ufw enable
```

**Verificar el estado:**

```
sudo ufw status verbose
```

**Salida esperada:**

```
Status: active

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere
80/tcp                     ALLOW       Anywhere
443/tcp                    ALLOW       Anywhere
3000/tcp                   ALLOW       Anywhere
```

## 📦 Instalación de Dokploy

**Ejecuta:**

```
curl -sSL [https://dokploy.com/install.sh](https://dokploy.com/install.sh) | sh
```

**El proceso tarda 3-5 minutos y verás:**

- Instalación de dependencias.
- Descarga de imágenes Docker.
- Configuración automática de servicios.
- Mensaje de éxito con la URL de acceso.

### Verificar la Instalación

```
# Ver contenedores de Docker activos
sudo docker ps
```

### Primer Acceso

**Por IP (temporal):**

Abre tu navegador y ve a: `http://[IP_DEL_SERVIDOR]:3000`

**⚠️ Importante:**

- Este acceso es temporal solo para verificar que funciona.
- En el siguiente paso configuraremos el dominio con SSL.
- **NO uses esta URL en producción.**

## 🌍 Configuración de Dominios y DNS

### Registros DNS

Ve al panel de administración de tu dominio (ej. DigitalOcean, Namecheap, Cloudflare) y configura:

|   |   |   |   |   |
|---|---|---|---|---|
|**Tipo**|**Hostname**|**Valor**|**TTL**|**Descripción**|
|**A**|`dokploy`|`[IP_DEL_SERVIDOR]`|3600|Apunta al Panel de Dokploy|
|**A**|`@`|`[IP_DEL_SERVIDOR]`|3600|Raíz del dominio (opcional)|

**Explicación:**

- `dokploy` → `dokploy.tu-dominio.com` (acceso al panel).

### Verificar Propagación de DNS

```
# Verificar subdominio de Dokploy
dig dokploy.tu-dominio.com +short
```

**Nota:** La propagación DNS puede tardar de 5 minutos a 48 horas (usualmente es rápida en proveedores modernos).

## 🏗️ Arquitectura del Sistema

### ¿Cómo Funciona el SSL Automático?

1. **Creas una aplicación en Dokploy** y asignas un dominio (ej: `app.tu-dominio.com`).
2. **Activas HTTPS** en la configuración de la app.
3. **Traefik automáticamente:**
    - Detecta el nuevo dominio.
    - Solicita un certificado a Let's Encrypt.
    - Valida el dominio (por eso necesitas el puerto 80 abierto).
    - Instala el certificado.
    - Renueva automáticamente antes de que expire.

**Todo esto sin que tengas que ejecutar comandos en la terminal.**

## ⚙️ Configuración del Panel de Dokploy

### Paso 1: Acceso Inicial por Dominio

Espera a que el DNS propague y luego accede a:

`http://dokploy.tu-dominio.com:3000`

**⚠️ Nota:** Inicialmente usarás el puerto 3000 sin SSL hasta completar la configuración interna.

### Paso 2: Setup Inicial

1. **Crea tu cuenta de administrador:**
    - Email: `admin@tu-dominio.com`
    - Contraseña: (usa una contraseña robusta)
    - Confirma contraseña
2. **Completa el asistente de configuración.**

### Paso 3: Configurar SSL para el Panel de Dokploy

#### En el Panel de Dokploy:

1. Ve a **Settings** (⚙️) en el menú lateral.
2. Busca la sección **Server** o **General**.
3. Encuentra **Server Domain Configuration**.
4. Configura:
    - **Domain:** `dokploy.tu-dominio.com`
    - **Let's Encrypt Email:** `admin@tu-dominio.com`
    - **Enable HTTPS:** ✅ **Activado**
    - **Certificate Provider:** `Let's Encrypt`
5. **Guarda los cambios.**

### Paso 4: Verificación Final

Después de 2-3 minutos, accede a:

`https://dokploy.tu-dominio.com` 🔒

**Deberías ver:**

- ✅ Candado verde en el navegador.
- ✅ Certificado válido emitido por "Let's Encrypt".
- ✅ Redirección automática de HTTP a HTTPS.
- ✅ Ya no es necesario usar el puerto `:3000`.