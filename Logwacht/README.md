# Logwatch - Monitoreo y Análisis de Logs en Linux

## Introducción

**Logwatch** es una herramienta de monitoreo y análisis de registros en sistemas Linux. Su función principal es analizar los archivos de log almacenados en `/var/log/` y generar informes detallados con información relevante sobre la actividad del sistema.

## Instalación

Para instalar Logwatch en sistemas basados en Debian/Ubuntu, ejecuta:

```bash
sudo apt update && sudo apt install logwatch -y
```

## Uso Básico

### 1. Generar un informe detallado del día actual en pantalla:

```bash
logwatch --detail High --range today --service all --output stdout
```


![](ANEXOS/Pasted%20image%2020250327172230.png)


### 2. Generar un informe y enviarlo por correo:

```bash
logwatch --detail Medium --range yesterday --mailto admin@ejemplo.com
```

### 3. Analizar solo los intentos de acceso SSH de los últimos 7 días:

```bash
logwatch --detail High --range "between -7 days and today" --service sshd --output stdout
```

### 4. Guardar el informe en un archivo:

```bash
logwatch --detail High --range today --service all --filename /root/logwatch-report.log
```

## Configuración Avanzada

Logwatch permite personalizar su comportamiento editando su archivo de configuración principal:

```bash
sudo nano /etc/logwatch/conf/logwatch.conf
```

Algunas opciones que puedes modificar incluyen:

- `Detail = Low|Med|High` → Nivel de detalle del informe.
- `Output = stdout|file|mail` → Dónde se mostrará el resultado.
- `Format = text|html` → Formato del informe.
- `MailTo = admin@ejemplo.com` → Dirección de correo para recibir los informes.

## Automatización con Cron

Para ejecutar Logwatch diariamente y recibir informes automáticos, puedes agregar una tarea en `cron`:

```bash
sudo crontab -e
```

Y agregar la siguiente línea:

```bash
0 7 * * * /usr/sbin/logwatch --output mail --mailto admin@ejemplo.com --detail High --range yesterday
```

Esto ejecutará Logwatch todos los días a las 7:00 AM y enviará el informe por correo.
