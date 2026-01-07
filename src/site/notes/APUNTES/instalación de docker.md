---
{"dg-publish":true,"permalink":"/apuntes/instalacion-de-docker/","tags":["referencias","web/documentación"]}
---


![[MOC.base]]

# instalación de docker

## ubuntu server

La manera mas simple sería a traves del script oficial[^1]

```
curl -fsSL https://get.docker.com -o install-docker.sh
sudo sh install-docker.sh
```

**Lo que hace este script:**

- Detecta que estás en Ubuntu.
- Agrega las llaves GPG y el repositorio.
- Instala Docker Engine, CLI, Compose y Containerd.
- Configura los servicios para que inicien con el sistema.

luego de eso hay que dar permisos al usuario para utilizarlo sin usar el sudo

Añadir tu usuario al grupo:

```
sudo usermod -aG docker $USER
```

Aplicar los cambios inmediatamente (sin reiniciar):

```
newgrp docker
```

---

para saber utilizar docker aquí una [[APUNTES/lista de comandos de docker\|lista de comandos de docker]]

---

## windows

instalación del docker desktop desde [[uniget\|uniget]] y [[winget\|winget]]  y seguir la configuración de [[APUNTES/wsl\|wsl]] después

---

[^1]: https://get.docker.com
