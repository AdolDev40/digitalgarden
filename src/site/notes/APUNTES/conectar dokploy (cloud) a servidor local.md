---
{"dg-publish":true,"permalink":"/apuntes/conectar-dokploy-cloud-a-servidor-local/","tags":["ideas"]}
---


![[MOC.base]]

# Conectar dokploy (cloud) a servidor local

Esta guía explica cómo conectar Dokploy a un servidor local [^1].

lo vamos a realizar a traves de un vpn, con la herramienta tailscale

para ello lo vamos a instalar:

```
curl -fsSL https://tailscale.com/install.sh | sh
```

luego iniciamos sesión:

```
sudo tailscale up
```

> [!NOTE] 
> Esto se realiza en las dos maquinas, el servidor local y el de la nube

**En la Laptop Samsung:**

Necesitas la IP interna de Tailscale. Ejecuta:

```
tailscale ip -4
```

## **ahora En dokploy con la clave ssh:**

![Pasted image 20251230102514.png](/img/user/ANEXO/Pasted%20image%2020251230102514.png)

1. En el sidebard vamos hacia ssh keys
2. Luego agregamos la clave
3. Y se genera la conexión

---

![Pasted image 20251230102804.png](/img/user/ANEXO/Pasted%20image%2020251230102804.png)

genera las claves y copiamos la clave publica

---

## **ahora En la samsung pegando la clave pública:**

Es completamente normal. En una instalación limpia de Ubuntu Server, la carpeta `.ssh` y el archivo `authorized_keys` **no se crean automáticamente** hasta que se necesitan.

creamos el directorio y el archivo:

```
mkdir -p ~/.ssh
touch ~/.ssh/authorized_keys
```

Ajustamos los permisos:

```
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

pegamos la llave ssh publica:

```
nano ~/.ssh/authorized_keys
```

## **mejor Seguridad en el servidor samsung:**

```
# 1. Asegura que el puerto SSH esté abierto para tu red local primero
sudo ufw allow 22/tcp

# 2. Permite todo lo de Tailscale (para Dokploy)
sudo ufw allow in on tailscale0

# 3. Configura las políticas por defecto
sudo ufw default deny incoming
sudo ufw default allow outgoing

# 4. Activa el firewall (presiona 'y' cuando pregunte)
sudo ufw enable
```

## **siguiendo Con la configuración y finalizando:**

![Pasted image 20251230104337.png](/img/user/ANEXO/Pasted%20image%2020251230104337.png)

1. configuramos la ip del servidor
2. Y el nombre de usuario, el usuario del servidor local

> [!NOTE] 
> La ip es la de tailscale de tu servidor local
> ```
> tailscale ip -4 # con este comando puedes ver la ip
> ```

![Pasted image 20251230105520.png](/img/user/ANEXO/Pasted%20image%2020251230105520.png)

De funionar puedes entrar tranquilamente a la terminal

---

![Pasted image 20251230105448.png](/img/user/ANEXO/Pasted%20image%2020251230105448.png)

Y fácilmente se conectara

---

[^1]: esta configuración es para [[APUNTES/servidor con laptop samsung np300\|servidor con laptop samsung np300]] mayormente y [[APUNTES/configurar vps de digital ocean\|documentación del vps adoldev.xyz]]
