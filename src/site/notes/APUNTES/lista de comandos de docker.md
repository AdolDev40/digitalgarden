---
{"dg-publish":true,"permalink":"/apuntes/lista-de-comandos-de-docker/","tags":["referencias","listas"]}
---


![[MOC.base]]

# 2025-12-23 lista de comandos de docker

lista de comandos[^1]

1. Para iniciar los servicios en modo separado: `docker-compose up -d`
2. Para iniciar los servicios y ver los registros: `docker-compose up`
3. Para detener los servicios: `docker-compose down`
4. Para detener y eliminar contenedores, redes: `docker-compose down`
5. Para eliminar todo con respecto al compose: `docker-compose down --rmi all -v --remove-orphans`
6. Para pausar los servicios: `docker-compose pause`
7. Para reanudar (despausar) los servicios: `docker-compose unpause`
8. Para reiniciar los servicios: `docker-compose restart`
9. Para ver los registros: `docker-compose logs`
10. Para ver los registros en tiempo real: `docker-compose logs -f`
11. Para eliminar contenedores detenidos: `docker-compose rm`
12. Para eliminar volúmenes: `docker-compose down -v`
13. Para reconstruir e iniciar: `docker-compose up --build`
14. Para escalar un servicio (ej. odoo a 2 instancias): `docker-compose up -d --scale odoo=2`
15. Para listar contenedores en ejecución: `docker-compose ps`
16. Para ejecutar un comando en un contenedor en ejecución (ej. bash en odoo): `docker-compose exec odoo bash`

---

[^1]: https://gemini.google.com/share/811acab962fc