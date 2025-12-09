---
{"dg-publish":true,"permalink":"/apuntes/configuracion-de-cloudflared-tunnel/","tags":["referencias","web/documentación"]}
---


## Objetivo

Compartir mi localhost para mostrar la aplicación y que estén probándolo.

## Requisitos previos

- Dominio registrado (Hostinger en este caso).
- Cuenta gratuita en Cloudflare.
- `cloudflared` instalado en la máquina local (Windows).
	- esto se realiza por [[uniget\|uniget]]
	- o realizando el siguiente comando en la terminal: `winget install --id Cloudflare.cloudflared`[^1]

## Configuración del Dominio

Para que Cloudflare gestione los certificados SSL y el enrutamiento, debe ser la autoridad DNS.

1. **En Cloudflare:** Añadir el sitio (ej. `midominio.com`) seleccionando el Plan Gratuito.
    
2. **En el Registrador de Dominio:** Cambiar los _Nameservers_ actuales por los dos proporcionados por Cloudflare.
    
3. **Estado:** Esperar a que el dominio aparezca como **"Active"** en el panel de Cloudflare.

## Túnel simple

```
cloudflared tunnel --url http://localhost
```

> [!NOTE] 
> cloudflare asignara un dominio aleatorio a tu localhost el cual puedes compartir

![Pasted image 20251208175341.png](/img/user/ANEXO/Pasted%20image%2020251208175341.png)

![Pasted image 20251208175442.png](/img/user/ANEXO/Pasted%20image%2020251208175442.png)

## Creación del Túnel (Named Tunnel)

A diferencia de los túneles rápidos (`--url`), un túnel con nombre es persistente y estable.

### Autenticación

Abrir PowerShell y ejecutar:

```
cloudflared tunnel login
```

> [!NOTE] 
> Se abrirá el navegador. Seleccionar el dominio a autorizar.

### Creación del Túnel

Crear el túnel asignándole un nombre identificativo (ej. `mi-servidor-dev`):

```
cloudflared tunnel create mi-servidor-dev
```

> [!NOTE] 
> El sistema generará un archivo JSON con credenciales y un UUID único.

### Enrutamiento DNS

Vincular el túnel al subdominio deseado (ej. `app.midominio.com`):

```
cloudflared tunnel route dns mi-servidor-dev app.midominio.com
```

> [!NOTE] 
> Esto crea automáticamente el registro CNAME en Cloudflare apuntando al túnel.

### Ejecución

```
cloudflared tunnel run --url http://localhost mi-servidor-dev
```

> [!NOTE] 
> Esto comparte el localhost al dominio o subdominio configurado

![Pasted image 20251208175640.png](/img/user/ANEXO/Pasted%20image%2020251208175640.png)

![Pasted image 20251208175738.png](/img/user/ANEXO/Pasted%20image%2020251208175738.png)

## Referencias

[^1]: https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel/downloads/
