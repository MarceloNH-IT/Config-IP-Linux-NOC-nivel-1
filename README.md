# 🌐 Configuración Básica de IP en Linux (Nivel 1)

Este práctico demuestra cómo un operador de nivel 1 puede:
- Ver la configuración de red.
- Cambiar la IP manualmente.
- Validar conectividad con ping y nslookup.

---

## 📊 Paso 1 – Configuración inicial
![IP Actual](assets/linux-ip/s1.jpeg)

---

## 🛠️ Paso 2 – Intento de ifconfig
![Ifconfig Error](assets/linux-ip/s2.jpeg)

---

## 🛠️ Paso 3 – Edición de Netplan
![Netplan Config](assets/linux-ip/s3.jpeg)

---

## 📌 Paso 4 – Aplicar cambios
![Netplan Apply](assets/linux-ip/s4.jpeg)

---

## 📊 Paso 5 – Validación
**Ping al gateway**
![Ping Gateway](assets/linux-ip/s5.jpeg)

**Ping a Google**
![Ping Google](assets/linux-ip/s6.jpeg)

**Prueba DNS**
![NSLookup](assets/linux-ip/s7.jpeg)

**Ping repetido a Google**
![Ping Google 2](assets/linux-ip/s8.jpeg)

---

## ✅ Observacion
Este ejercicio muestra que:
- La IP fija se configuró correctamente.  
- El ping al gateway y a Google falló → sin salida a Internet.  
- El DNS resolvió correctamente → servicio operativo.  

> 📌 Observación: El operador de nivel 1 documenta los resultados y escala la incidencia al área de redes para revisión.



### Conceptos básicos

- **[IP](ca://s?q=Que_es_una_IP_en_redes)**: número único que identifica un dispositivo en la red.  
- **[Máscara de red](ca://s?q=Que_es_una_mascara_de_red)**: define el rango de hosts disponibles dentro de la red.  
- **[Gateway](ca://s?q=Que_es_un_gateway_en_redes)**: dispositivo que conecta tu red local con otras redes (ej. Internet).  
- **[DNS](ca://s?q=Que_es_el_DNS_y_como_funciona)**: traduce nombres de dominio (google.com) a direcciones IP.

  📊 Estadísticas y contadores
## 📈 Estadísticas de GitHub

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=MarceloNH-IT&show_icons=true&theme=radical)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=MarceloNH-IT&layout=compact&theme=radical)

![Streak Stats](https://github-readme-streak-stats.herokuapp.com/?user=MarceloNH-IT&theme=radical)

![Profile Views](https://komarev.com/ghpvc/?username=MarceloNH-IT&color=blue&style=flat)

### 🏁 Conclusión

El ejercicio demuestra que un operador de nivel 1 puede:
- Configurar IP, máscara y gateway en Linux.  
- Ejecutar pruebas de conectividad con ping y nslookup.  
- Interpretar resultados: IP correcta, DNS operativo, pero sin salida a Internet.  
- Documentar con capturas y observaciones claras.  

📌 Observación: Se recomienda escalar al área de redes para revisar la configuración de VirtualBox (NAT/Bridge) y asegurar conectividad externa.

Voy a subir la prueba nivel 2 para resolver el problema. 

Gracias por visitarme y les envio un saludo grande. 


