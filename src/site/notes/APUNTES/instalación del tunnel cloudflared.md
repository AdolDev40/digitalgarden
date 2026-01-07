---
{"dg-publish":true,"permalink":"/apuntes/instalacion-del-tunnel-cloudflared/","tags":["referencias"]}
---


![[MOC.base]]

# instalación del tunnel cloudflared

## Ubuntu server:

En lugar de tener un script para cada versión, puedes usar `$(lsb_release -cs)`. Este comando detecta automáticamente si estás en _Focal_, _Jammy_ o _Noble_.[^1]

```
# 1. Crear el directorio y descargar la llave
sudo mkdir -p --mode=0755 /usr/share/keyrings
curl -fsSL https://pkg.cloudflare.com/cloudflare-main.gpg | sudo tee /usr/share/keyrings/cloudflare-main.gpg >/dev/null

# 2. Agregar SOLO el repositorio estable
echo 'deb [signed-by=/usr/share/keyrings/cloudflare-main.gpg] https://pkg.cloudflare.com/cloudflared any main' | sudo tee /etc/apt/sources.list.d/cloudflared.list

# 3. Instalar
sudo apt-get update && sudo apt-get install cloudflared
```

---

Luego sigue la [[APUNTES/configuración de cloudflared tunnel\|configuración de cloudflared tunnel]]

---

[^1]: https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel/downloads/
