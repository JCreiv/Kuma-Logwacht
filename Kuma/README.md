## KUMA

### **¿Qué es Uptime Kuma?**

[Uptime Kuma](https://github.com/louislam/uptime-kuma) es una herramienta de monitorización de servicios de código abierto que permite supervisar la disponibilidad de servidores, sitios web y aplicaciones mediante comprobaciones periódicas. Es una alternativa ligera y autohospedada a servicios como UptimeRobot.

### **Ejecutando Uptime Kuma con Docker**

El siguiente comando permite desplegar Uptime Kuma en un contenedor Docker:

```bash
docker run -d --restart=always -p 3001:3001 -v uptime-kuma:/app/data --name uptime-kuma louislam/uptime-kuma:1
```


Una vez ejecutado el contenedor, se puede acceder a la interfaz web desde un navegador en la dirección:

http://localhost:3001

Desde ahí, se pueden agregar monitores para supervisar servidores, sitios web, bases de datos y otros servicios.







![](ANEXOS/Pasted%20image%2020250327160534.png)
Ejemplo con un servidor en express en el puerto 3000 en un vps


![](ANEXOS/Pasted%20image%2020250327160616.png)
Ejemplo con una pagina que queramos monitorizar en este caso marca.com

![](ANEXOS/Pasted%20image%2020250327161108.png)

Cuando corto el servidor de express nos lo muestra como caido



![](ANEXOS/Imagen%20de%20WhatsApp%202025-03-27%20a%20las%2016.52.38_c9fc57fd.jpg)

Podemos vincularlo con telegram o incluso discord en este caso lo he vinculado con telegram
