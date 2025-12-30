---
{"dg-publish":true,"permalink":"/apuntes/digital-garden/","tags":["ideas","web/documentación"]}
---


![[MOC.base]]

# digital garden[^5]

Esto sería la manera mas fácil de generar documentación para aplicativos que estas desarrollando.

Comenzamos descargando el plugin[^1], entrando en la documentación nos manda a un repositorio[^2], del cual creamos una bifurcación.

Una ves copiado el repositorio[^3], seguimos la configuración del repositorio del plugin[^2]

Creamos un token de acceso para el plugin pueda leer y escribir sobre el repositorio[^4].

![Pasted image 20251207021953.png](/img/user/ANEXO/PNG/Pasted%20image%2020251207021953.png)

Luego procedemos a realizar despliegues con dokploy.

![Pasted image 20251207022050.png](/img/user/ANEXO/PNG/Pasted%20image%2020251207022050.png)

![Pasted image 20251207022209.png](/img/user/ANEXO/PNG/Pasted%20image%2020251207022209.png)

Desplegamos el proyecto

![Pasted image 20251207022245.png](/img/user/ANEXO/PNG/Pasted%20image%2020251207022245.png)

> [!NOTE] NOTA
> 1. en el servidor solo tenemos habilitado el puerto 80
> 2. este sería el dominio que vamos a utilizar
> 3. y la configuración con respecto al ssl

![Pasted image 20251207022347.png](/img/user/ANEXO/PNG/Pasted%20image%2020251207022347.png)

Luego verificamos vemos en que ip esta, una ves vista procedemos a configurar en hostinger los dns, como se muestra la imagen actualmente tenemos configurado esos tres.

![Pasted image 20251207022816.png](/img/user/ANEXO/PNG/Pasted%20image%2020251207022816.png)

validamos los dns, y ya tendremos subida la página web.

![Pasted image 20251207023014.png](/img/user/ANEXO/PNG/Pasted%20image%2020251207023014.png)

---

[^1]: [github - pligin digital garden](https://github.com/oleeskild/obsidian-digital-garden)

[^2]: https://github.com/oleeskild/digitalgarden

[^3]: [turepo]

[^4]: https://github.com/settings/personal-access-tokens/new

[^5]: [[APUNTES/obsidian\|obsidian]]
