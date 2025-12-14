---
{"dg-publish":true,"permalink":"/apuntes/2025-11-11-laboratorio-1-configuracion-de-ssh/","tags":["tarea"]}
---


# laboratorio 1 configuración de ssh

## Instrucciones 

Para realizar este laboratorio tendrá que utilizar el packet tracer y subir un archivo con los siguientes requerimientos, también utilizará su numero de cuenta, como ejemplo tomaremos el siguiente 20003000348, entonces el valor de X sera sustituido por los últimos dos números de su cuenta, en este caso 48

> En mi caso voy a estar utilizando 06

<style> .container {font-family: sans-serif; text-align: center;} .button-wrapper button {z-index: 1;height: 40px; width: 100px; margin: 10px;padding: 5px;} .excalidraw .App-menu_top .buttonList { display: flex;} .excalidraw-wrapper { height: 800px; margin: 50px; position: relative;} :root[dir="ltr"] .excalidraw .layer-ui__wrapper .zen-mode-transition.App-menu_bottom--transition-left {transform: none;} </style><script src="https://cdn.jsdelivr.net/npm/react@17/umd/react.production.min.js"></script><script src="https://cdn.jsdelivr.net/npm/react-dom@17/umd/react-dom.production.min.js"></script><script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@excalidraw/excalidraw@0/dist/excalidraw.production.min.js"></script><div id="laboratorio_1_configuración_de_ssh_2025-09-18_1541.38.excalidraw.md1"></div><script>(function(){const InitialData={"type":"excalidraw","version":2,"source":"https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.15.3","elements":[{"id":"p3fFHGYolfUXvkmV9PS5Y","type":"image","x":241.8753934321524,"y":-43.050445556640625,"width":584,"height":225,"angle":0,"strokeColor":"transparent","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"a1","roundness":null,"seed":1936157318,"version":83,"versionNonce":679009434,"isDeleted":false,"boundElements":[],"updated":1758231809411,"link":null,"locked":false,"status":"pending","fileId":"f5ecf9cae41a7f06e7cc765eeb6ff56a8cd600c3","scale":[1,1],"crop":null},{"id":"Xe9yp4YA","type":"text","x":308.36778709316775,"y":-85.00824073500263,"width":186.6798858642578,"height":25,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"a2","roundness":null,"seed":781827162,"version":26,"versionNonce":824639450,"isDeleted":false,"boundElements":[],"updated":1758231883261,"link":null,"locked":false,"text":"192.168.06.254/24","rawText":"192.168.06.254/24","fontSize":20,"fontFamily":5,"textAlign":"left","verticalAlign":"top","containerId":null,"originalText":"192.168.06.254/24","autoResize":true,"lineHeight":1.25},{"id":"o0T89vhk","type":"text","x":653.2058837118201,"y":-89.84014991469013,"width":187.13987731933594,"height":25,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"a3","roundness":null,"seed":718060038,"version":68,"versionNonce":217999642,"isDeleted":false,"boundElements":[],"updated":1758231894113,"link":null,"locked":false,"text":"192.168.06.253/24","rawText":"192.168.06.253/24","fontSize":20,"fontFamily":5,"textAlign":"left","verticalAlign":"top","containerId":null,"originalText":"192.168.06.253/24","autoResize":true,"lineHeight":1.25},{"id":"7l16mr2h","type":"text","x":262.1320311727576,"y":198.26193056004726,"width":162.61990356445312,"height":25,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"a4","roundness":null,"seed":1757686982,"version":65,"versionNonce":1823410714,"isDeleted":false,"boundElements":[],"updated":1758232283347,"link":null,"locked":false,"text":"192.168.06.2/24","rawText":"192.168.06.2/24","fontSize":20,"fontFamily":5,"textAlign":"left","verticalAlign":"top","containerId":null,"originalText":"192.168.06.2/24","autoResize":true,"lineHeight":1.25},{"id":"jWz1EPZQ","type":"text","x":700.3100096883826,"y":202.643705462391,"width":160.77989196777344,"height":25,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"transparent","fillStyle":"solid","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"a5","roundness":null,"seed":1832141446,"version":39,"versionNonce":665169626,"isDeleted":false,"boundElements":[],"updated":1758231931361,"link":null,"locked":false,"text":"192.168.06.3/24","rawText":"192.168.06.3/24","fontSize":20,"fontFamily":5,"textAlign":"left","verticalAlign":"top","containerId":null,"originalText":"192.168.06.3/24","autoResize":true,"lineHeight":1.25},{"id":"Py6Cd9B0nwAOyh3UMayqs","type":"rectangle","x":288.64979339017714,"y":-37.90411184926353,"width":140.21697998046875,"height":25.1409912109375,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#1e1e1e","fillStyle":"hachure","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"a7","roundness":{"type":3},"seed":1789398618,"version":74,"versionNonce":577617734,"isDeleted":false,"boundElements":[],"updated":1758232258190,"link":null,"locked":false},{"id":"VYsAW3LEGRZqe973q6Z0E","type":"rectangle","x":641.383161310099,"y":-36.233793245747904,"width":140.21697998046875,"height":25.1409912109375,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#1e1e1e","fillStyle":"hachure","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"a9","roundness":{"type":3},"seed":460487942,"version":119,"versionNonce":829574150,"isDeleted":false,"boundElements":[],"updated":1758232271009,"link":null,"locked":false},{"id":"d9xcpRtfjUplVu2ZZMKsu","type":"rectangle","x":238.84500470167097,"y":154.9593252447738,"width":140.21697998046875,"height":25.1409912109375,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#1e1e1e","fillStyle":"hachure","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"aA","roundness":{"type":3},"seed":2129101446,"version":125,"versionNonce":136809094,"isDeleted":false,"boundElements":[],"updated":1758233644099,"link":null,"locked":false},{"id":"OQS_KsgDcIVRiyRwjfW-q","type":"rectangle","x":687.3918283022865,"y":153.27826119761147,"width":140.21697998046875,"height":23.242954434397003,"angle":0,"strokeColor":"#1e1e1e","backgroundColor":"#1e1e1e","fillStyle":"hachure","strokeWidth":2,"strokeStyle":"solid","roughness":1,"opacity":100,"groupIds":[],"frameId":null,"index":"aB","roundness":{"type":3},"seed":1154345606,"version":172,"versionNonce":376099482,"isDeleted":false,"boundElements":[],"updated":1758233647679,"link":null,"locked":false}],"appState":{"theme":"light","viewBackgroundColor":"#ffffff","currentItemStrokeColor":"#1e1e1e","currentItemBackgroundColor":"#1e1e1e","currentItemFillStyle":"hachure","currentItemStrokeWidth":2,"currentItemStrokeStyle":"solid","currentItemRoughness":1,"currentItemOpacity":100,"currentItemFontFamily":5,"currentItemFontSize":20,"currentItemTextAlign":"left","currentItemStartArrowhead":null,"currentItemEndArrowhead":"arrow","currentItemArrowType":"round","currentItemFrameRole":null,"scrollX":-109.2016973696062,"scrollY":115.9448117287398,"zoom":{"value":1},"currentItemRoundness":"round","gridSize":20,"gridStep":5,"gridModeEnabled":false,"gridColor":{"Bold":"rgba(217, 217, 217, 0.5)","Regular":"rgba(230, 230, 230, 0.5)"},"currentStrokeOptions":null,"frameRendering":{"enabled":true,"clip":true,"name":true,"outline":true,"markerName":true,"markerEnabled":true},"objectsSnapModeEnabled":false,"activeTool":{"type":"selection","customType":null,"locked":false,"fromSelection":false,"lastActiveTool":null}},"files":{}};InitialData.scrollToContent=true;App=()=>{const e=React.useRef(null),t=React.useRef(null),[n,i]=React.useState({width:void 0,height:void 0});return React.useEffect(()=>{i({width:t.current.getBoundingClientRect().width,height:t.current.getBoundingClientRect().height});const e=()=>{i({width:t.current.getBoundingClientRect().width,height:t.current.getBoundingClientRect().height})};return window.addEventListener("resize",e),()=>window.removeEventListener("resize",e)},[t]),React.createElement(React.Fragment,null,React.createElement("div",{className:"excalidraw-wrapper",ref:t},React.createElement(ExcalidrawLib.Excalidraw,{ref:e,width:n.width,height:n.height,initialData:InitialData,viewModeEnabled:!0,zenModeEnabled:!0,gridModeEnabled:!1})))},excalidrawWrapper=document.getElementById("laboratorio_1_configuración_de_ssh_2025-09-18_1541.38.excalidraw.md1");ReactDOM.render(React.createElement(App),excalidrawWrapper);})();</script>

 para colocar las contraseñas, direcciones ip y banner motd. Las configuraciones a realizar en los dos switches son las siguientes:

1. Crear el nombre del dominio con su primer nombre  y apellido
2. Crear el nombre del usuario con su primer nombre en ambos switches
3. crear el ssh en ambos dispositivos con una llave de excriptacion de 1024 bits
4. permitir el uso solamente del ssh en ambos switches a traves de la red

---

## Paso a Paso de la tarea:

### **Paso 1: Entrar al modo de configuración global**

Para empezar a configurar el switch, debes pasar del modo de usuario (`>`) al modo privilegiado (`#`) y luego al modo de configuración global.

1. **Habilita el modo privilegiado.**

```
enable
```

2. **Entra al modo de configuración global.**

```
configure terminal
```

---

### **Paso 2: Configuración básica**

Ahora que estás en el modo de configuración global, puedes hacer las configuraciones iniciales.

3. **Asigna un nombre al switch.**

```
hostname Adolfo
```

4. **Establece un banner de mensaje.**

```
banner motd z ESTE EQUIPO ES PROPIEDAD DE ADOLFO JAFET LOPEZ OLIVA CON NUMERO DE CUENTA 20221001806 z
```

---

### **Paso 3: Configurar contraseñas**

La seguridad es fundamental. Aquí se configuran las contraseñas para los diferentes niveles de acceso.

5. **Establece una contraseña para el modo privilegiado (encriptada).**

```
enable secret cisco
```

6. **Encripta todas las contraseñas.**

```
service password-encryption
```

7. **Configura una contraseña para el acceso por consola.**

```
line console 0
password cisco
login
exit
```

8. **Configura una contraseña para el acceso remoto (Telnet).**

```
line vty 0 4
password cisco
login
exit
```

---

### **Paso 4: Configurar la dirección IP de gestión**

Para administrar el switch de forma remota, necesitas asignarle una dirección IP a su interfaz virtual (VLAN 1).

9. **Entra al modo de configuración de la interfaz VLAN 1.**

```
interface vlan 1
```

10. **Asigna la dirección IP y la máscara de subred.**

```
ip address 192.168.06.254 255.255.255.0
```

11. **Habilita la interfaz.**

```
no shutdown
```

12. **Sal del modo de configuración de la interfaz.**

```
exit
```

---

### **Paso 5: Guardar la configuración**

¡Este es el paso más importante! Si no guardas, perderás todos los cambios al reiniciar el switch.

13. **Guarda la configuración actual en el archivo de inicio.**

```
do copy running-config startup-config
```

### **Paso 6: Configurar equipo 1**

![{74ADCC5C-62C7-4FC2-B353-9C957F19F7FC}.png|600](/img/user/ANEXO/PNG/%7B74ADCC5C-62C7-4FC2-B353-9C957F19F7FC%7D.png)

Resultado de la configuración:

```shell
C:\>ipconfig

FastEthernet0 Connection:(default port)

   Connection-specific DNS Suffix..: 
   Link-local IPv6 Address.........: FE80::20D:BDFF:FE8C:CC0
   IPv6 Address....................: ::
   IPv4 Address....................: 192.168.6.2
   Subnet Mask.....................: 255.255.255.0
   Default Gateway.................: ::
                                     0.0.0.0

Bluetooth Connection:

   Connection-specific DNS Suffix..: 
   Link-local IPv6 Address.........: ::
   IPv6 Address....................: ::
   IPv4 Address....................: 0.0.0.0
   Subnet Mask.....................: 0.0.0.0
   Default Gateway.................: ::
                                     0.0.0.0

C:\>ping 192.168.6.254

Pinging 192.168.6.254 with 32 bytes of data:

Reply from 192.168.6.254: bytes=32 time<1ms TTL=255
Reply from 192.168.6.254: bytes=32 time<1ms TTL=255
Reply from 192.168.6.254: bytes=32 time<1ms TTL=255
Reply from 192.168.6.254: bytes=32 time<1ms TTL=255

Ping statistics for 192.168.6.254:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 0ms, Maximum = 0ms, Average = 0ms
```

>[!NOTE] NOTA!!!
>SE REALIZA LA MISMA CONFIGURACIÓN EN EL SWICH 2 Y PC DOS, CAMBIAR IP SEGÚN LA IMAGEN

### **Paso 7: Entrar al modo de configuración global**

1. **Habilita el modo privilegiado.**

```
enable
```

2. **Entra al modo de configuración global.**

```
configure terminal
```

### **Paso 8: Configuración de SSH**

Estos comandos son cruciales para asegurar la conexión remota a tus dispositivos.

3. **Configura el nombre de dominio.**

```
ip domain-name adolfo.lopez
```

4. **Genera la clave de encriptación.**

```
crypto key generate rsa
```

Cuando te lo pida, establece el tamaño de la clave. Un tamaño de **1024** es un buen estándar.

### **Paso 9: Configurar usuario local**

Para que el acceso a través de SSH sea seguro, se crea un usuario local.

5. **Crea un usuario y una contraseña.**

```
username adolfo secret cisco
```

### **Paso 10: Configurar las líneas de acceso**

Aquí es donde se aplica la configuración de SSH a las líneas de acceso remoto (VTY).

6. **Entra al modo de configuración de las líneas VTY.**

```
line vty 0 4
```

7. **Establece que el inicio de sesión use un usuario local.**

```
login local
```

8. **Permite únicamente el acceso por SSH y deshabilita Telnet.**

```
transport input ssh
```

9. **Sal del modo de configuración de la línea VTY.**

```
exit
```

### **Paso 11: Guardar la configuración**

10. **Guarda la configuración para que los cambios persistan después de un reinicio.**

```
end
copy running-config startup-config
```

### **Paso 12: Conectar equipo 1**

```shell
C:\>ssh -l adolfo 192.168.6.253

Password: 

 ESTE EQUIPO ES PROPIEDAD DE ADOLFO JAFET LOPEZ OLIVA CON NUMERO DE CUENTA 20221001806 

Adolfo>
```

# Referencias

- [Redes Laboratorio 1 configuraciones básicas de un equipo de red - YouTube](https://youtu.be/oB8w11rXqtc?si=G0frW7rou5DUcID9)
- [Redes LAboratorio 2, Configuración de SSh - YouTube](https://youtu.be/GzN3GTuUItM?si=FQwVHgxLhHzTRCm-)
- [‎Gemini - Configuración Básica de Switches CLI](https://g.co/gemini/share/2c55cb0b09ea)
- [[Adolfo_Lopez_ssh.pkt]]