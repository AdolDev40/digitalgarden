---
{"dg-publish":true,"permalink":"/apuntes/configurar-vps-de-digital-ocean/","tags":["referencias","web/documentación"]}
---


![[MOC.base]]

# Configurar vps de digital ocean

## Guía Paso a Paso: Creación del Droplet de 2 GB

### 1. Elige la Región (Ubicación)

Esta es la ubicación física del centro de datos donde se alojará tu servidor.

- **Selección:** Elige la región que sea más conveniente para ti o para tu público objetivo.
    - **Configuración:** En la imagen se muestra seleccionada **San Francisco**.

![Pasted image 20251205173103.png](/img/user/ANEXO/PNG/Pasted%20image%2020251205173103.png)

### 2. Elige la Imagen (Sistema Operativo) 

El sistema operativo recomendado es Ubuntu LTS, ya que es el estándar de la industria para servidores web.

- **Selección:** En la sección "Elige una imagen", selecciona la pestaña **"Ubuntu"**.
    - **Versión:** Elige la versión de **LTS (Long-Term Support)** más reciente, como **22.04 (LTS) x64**.

![Pasted image 20251205173126.png](/img/user/ANEXO/PNG/Pasted%20image%2020251205173126.png)

### 3. Selecciona el Tipo de Gotita (Plan)

Aquí eliges los recursos de CPU y memoria (RAM) que necesita tu servidor.

- **Tipo:** Elige la pestaña **"Básico"** y la opción **"Regular"** (Tipo de disco: SSD).
- **Recursos:** Selecciona el plan de **$12/mes**, que te ofrece **2 GB de RAM / 1 CPU**.
    - _Justificación:_ Los **2 GB de RAM** son necesarios para manejar la carga de **Docker** y **Dokploy**.

![Pasted image 20251205173144.png](/img/user/ANEXO/PNG/Pasted%20image%2020251205173144.png)

### 4. Elige el Método de Autenticación (SSH Llave)

La autenticación por clave SSH es el método más seguro, como lo confirmamos anteriormente.

- **Opción:** En la sección "Elija el método de autenticación", selecciona el botón **"SSH Llave"**.

![Pasted image 20251205173201.png](/img/user/ANEXO/PNG/Pasted%20image%2020251205173201.png)

### 5. Añade la Clave Pública SSH

Este paso vincula tu Droplet a la clave privada que generaste en tu computadora (`ssh-keygen`).

1. **Generación:** Si no la has generado, usa el comando `ssh-keygen -t ed25519` en tu terminal para obtener la clave pública.
2. **Pegar:** En la ventana de "Añada la clave pública SSH":
    - Copia y pega el contenido completo de tu archivo `.pub` en el campo **(1) "Contenido clave de SSH"**.
    - Dale un **(2) "Nombre"** fácil de recordar (ej: "MiLaptopDeTrabajo").
3. Haz clic en **"Add SSH Key"**.

![Pasted image 20251205173900.png](/img/user/ANEXO/PNG/Pasted%20image%2020251205173900.png)

### 6. Finaliza la Creación

- **Nombrar:** Dale un nombre único a tu Droplet (ej: `mi-vps-portfolio`).
- **Finalizar:** Haz clic en el botón **"Crear Droplet"** (no visible en las imágenes, pero es el paso final).

### 7. Reservamos la ip

1. Configuramos la ip por la cual nos vamos a conectar
2. En la sección de networking es la configuración de esto

![unnamed.png](/img/user/ANEXO/PNG/unnamed.png)

---

[[APUNTES/configuración obsoleta vps de digital ocean\|configuración obsoleta vps de digital ocean]]

Lo siguiente a realizar sería una [[APUNTES/configuración vps con Dokploy\|configuración vps con Dokploy]]