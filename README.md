# 🌐 Configuración Básica de IP en Linux

Este trabajo práctico demuestra cómo un operador de nivel 1 puede:
- Ver la configuración actual de red.
- Cambiar la IP manualmente.
- Validar conectividad con herramientas básicas.



## 📊 Paso 1 – Ver configuración actual
Comando:

    ip addr show 

iMAGEN
Primera captura → comando ip addr show mostrando la IP actual de tu interfaz (enp0s3).

    inet 192.168.50.100/24 brd 192.168.50.255 scope global eth0


🛠️ Paso 2 – Configurar IP manualmente

Segunda captura → intento de ifconfig (salió el aviso de que no está instalado, lo cual también sirve como evidencia).

Ahora seguimos con la parte de configuración manual de IP en Linux

Instalar net-tools (si querés usar ifconfig):

    sudo apt update
    sudo apt install net-tools

Confirmar IP actual  
Ya lo hicimos con ip addr show → tenémos la IP 192.0.2.200/24 en la interfaz enp0s3.
Configurar IP manualmente (Netplan)  
Aunque no actualiza repositorios, podemos editar el archivo de configuración:

    sudo nano /etc/netplan/01-netcfg.yaml

Ejemplo de configuración ficticia:

    network:
    version: 2
    renderer: networkd
    ethernets:
    eth0:
      dhcp4: no
      addresses: [192.168.60.100/24]
      gateway4: 192.168.60.1
      nameservers:
        addresses: [8.8.8.8, 1.1.1.1]

  Aplicar cambios:

    sudo netplan apply

##🔍 Paso 3 – Validar conectividad
Ping al gateway:
          
    ping -c 4 192.168.60.1

## Ping a un dominio externo:

    ping -c 4 google.com

Prueba DNS con nslookup:

    nslookup google.com

✅ Conclusión
Este procedimiento permite:

Confirmar la configuración de IP, máscara y gateway.

Validar que la red funciona correctamente.

Documentar con capturas de consola y panel de red.

config-ip-linux/
├── README.md
├── capturas/
│   ├── ipconfig.png
│   ├── cambio_ip.png
│   ├── ping.png
│   └── nslookup.png


### Validación de conectividad

**Ping al gateway**
![Ping Gateway](assets/linux-ip/ping-gateway.png)
> Resultado: Destination Host Unreachable → el gateway no responde.

**Ping a Google**
![Ping Google](assets/linux-ip/ping-google.png)
> Resultado: Destination Host Unreachable → sin salida a Internet.

**Prueba DNS**
![NSLookup](assets/linux-ip/nslookup.png)
> Resultado: Resolución correcta de google.com → DNS operativo.

La IP fija quedó aplicada (192.0.2.2/24).

El ping al gateway (192.0.2.1) devuelve Destination Host Unreachable.

El ping a Google también falla.

Sin embargo, el nslookup a google.com sí resolvió la dirección IP → eso significa que DNS funciona, pero no hay conectividad de red hacia afuera.

No siempre todas las pruebas van a salir bien, de todas formas vamos a encontrar el problema y resolverlo. 



