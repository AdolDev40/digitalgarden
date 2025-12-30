---
{"dg-publish":true,"permalink":"/apuntes/tailscale/","tags":["referencias"]}
---


![[MOC.base]]

**Tailscale** es lo que se conoce como una **Mesh VPN** (red privada en malla).1 A diferencia de las VPN tradicionales (donde todo el tráfico va a un servidor central), Tailscale conecta tus dispositivos directamente entre sí (punto a punto) creando una red virtual segura, sin importar en qué parte del mundo estén o si están detrás de un firewall o un router doméstico.2

En tu caso, es la "pieza mágica" que permite que tu VPS en la nube y tu laptop Samsung en casa hablen entre sí como si estuvieran conectadas al mismo switch, de forma cifrada y privada.

---

## Conceptos Clave

- **Tailnet:** Es el nombre de tu red privada donde solo viven tus dispositivos.
- **MagicDNS:** Te permite acceder a tus equipos por nombre (ej: `http://samsung-server`) en lugar de recordar IPs.
- **Nodos:** Cada dispositivo (laptop, móvil, VPS) que conectas a la red.

---

## Guía de Instalación y Uso

### 1. Crear una cuenta

Primero, ve a [tailscale.com](https://tailscale.com) y regístrate (puedes usar tu cuenta de Google o GitHub).3 Es gratis para uso personal hasta 100 dispositivos.4

### 2. Instalación en Linux (Tu VPS y tu Samsung)

En ambos servidores, el proceso es idéntico y muy sencillo:

```
# Descarga e instala automáticamente
curl -fsSL https://tailscale.com/install.sh | sh
```

### 3. Autenticación (Vincular el equipo)

Una vez instalado, debes "loguear" el servidor a tu cuenta:

```
sudo tailscale up
```

- Aparecerá un enlace en la terminal.
- Cópialo y pégalo en el navegador de tu computadora principal.5
- Haz clic en **Connect** y el servidor quedará vinculado.

---

### Comandos de Uso Frecuente

|**Objetivo**|**Comando**|
|---|---|
|**Ver la IP de Tailscale**|`tailscale ip -4`|
|**Ver estado de la red**|`tailscale status`|
|**Desconectarse de la VPN6**|`sudo tailscale down`7|
|**Ver ayuda completa**|`tailscale --help`|

---

### ¿Por qué es perfecto para tu proyecto Dokploy?

1. **Seguridad:** No tienes que abrir puertos en tu router.8 El tráfico viaja por un túnel cifrado (WireGuard).9
2. **IP Estática:** Aunque el Wi-Fi de tu casa cambie de IP pública, la IP de Tailscale de la Samsung (`100.x.y.z`) **nunca cambiará**. Esto es vital para que Dokploy no pierda la conexión.10
3. **Acceso Total:** Puedes instalar Tailscale en tu teléfono o tu computadora personal y entrar a la laptop Samsung por SSH desde una cafetería usando la misma IP de siempre.

## Aplicación practicas:

[[APUNTES/conectar dokploy (cloud) a servidor local\|conectar dokploy (cloud) a servidor local]]