---
{"dg-publish":true,"permalink":"/apuntes/configurar-cloudflared-en-dokploy/","tags":["referencias"]}
---


![[MOC.base]]

# configurar cloudflared en dokploy

Esto se realiza para agregar multiples dominios sin entrar al panel de cloudflared para una configuración.[^1]
Esto entraría dentro de los [[servicios dentro de dokploy\|servicios dentro de dokploy]]
esto tambien es la [[APUNTES/configuración de cloudflared tunnel\|configuración de cloudflared tunnel]] pero dentro de dokploy

Utilizamos una plantilla de dokploy para utilizar cloudflared.

![Pasted image 20260106135514.png](/img/user/ANEXO/Pasted%20image%2020260106135514.png)

Luego tenemos a nuestra disposición un archivo docker compose en el cual hay que agregar la api.

---

```yml
services:
  cloudflared:
    image: 'cloudflare/cloudflared:latest'
    environment:
      - 'TUNNEL_TOKEN=${CLOUDFLARE_TUNNEL_TOKEN}'
    # ELIMINAMOS network_mode: host
    networks:
      - dokploy-network
    restart: unless-stopped
    command: [
      "tunnel",
      "--no-autoupdate",
      "run"
    ]

networks:
  dokploy-network:
    external: true
```

El docker compose de la foto hay que cambiarlo ya que tenemos problemas con el `network_mode: host` esto es porque compartia la misma red que el servidor ubuntu. por ello aplicamos lo siguiente:

```yml
services:
	networks:
      - dokploy-network
        
networks:
  dokploy-network:
    external: true
```

Dokploy crea una red central llamada **`dokploy-network`**. Todos los servicios importantes (como el panel de control y el proxy Traefik) viven ahí. y utilizamos `external: true` esto le estás diciendo a Docker: _"No crees una red nueva; usa la que ya creó Dokploy"_. Esto es lo que permite que el túnel se "enchufe" a la red donde ya están funcionando 

---

Para obtener el token hay que entrar en https://one.dash.cloudflare.com/

---

![Pasted image 20260106140626.png](/img/user/ANEXO/Pasted%20image%2020260106140626.png)

1. en el buscador ponemos la ruta señalada
2. creamos el tunnel
	1. dentro de este apartado nombramos el tunnel
	2. copiamos la api

![Pasted image 20260106140902.png](/img/user/ANEXO/Pasted%20image%2020260106140902.png)

seleccionamos obtenerla por docker 

---

Agregamos el token en variables de entorno:

![Pasted image 20260106140350.png](/img/user/ANEXO/Pasted%20image%2020260106140350.png)

luego solo lo desplegamos en zero trust lo vemos activo

![Pasted image 20260106141852.png](/img/user/ANEXO/Pasted%20image%2020260106141852.png)

---

Elegimos la siguiente configuración sobre ssl:

![Pasted image 20260106224251.png](/img/user/ANEXO/Pasted%20image%2020260106224251.png)

---

En https://dash.cloudflare.com/

tambien se realiza la siguiente configuración del dns:

- **Registro CNAME:** Creamos un registro que apunta al identificador de tu túnel (`[tunnel-id].cfargotunnel.com`) en lugar de a una IP.
- **El Comodín (`*`):** Al usar el asterisco (`*.adoldev.xyz`), le dijiste a Cloudflare: _"Cualquier cosa que termine en.adoldev.xyz (como odoo, test o dev) envíala a mi túnel"_.
- **Proxy (Nube Naranja):** Activamos el proxy para que Cloudflare oculte tu IP real y proporcione el certificado SSL (HTTPS) automáticamente.

---

Ahora en https://one.dash.cloudflare.com/ configuramos de la siguiente manera. 

![Pasted image 20260106224640.png](/img/user/ANEXO/Pasted%20image%2020260106224640.png)

> [!NOTE] 
> En los proyectos que se vallan creando hay que agregar `networks: - dokploy-network` en cada servicio

---


[^1]: https://docs.dokploy.com/docs/core/guides/cloudflare-tunnels
