# Monitorizacion

# Práctica de monitorización en Ubuntu

## 1. Procesos y CPU

### PS
Muestra los procesos activos y su consumo de recursos.

```bash
ps aux
ps -ef
```
Opciones: `a` procesos asociados a terminales, `u` información detallada, `x` incluye procesos sin terminal.

![PS](Capturas/ps.png)

### TOP
Monitoriza procesos, CPU y RAM en tiempo real.

```bash
top
top -d 2
```
Opciones: `-d` intervalo de actualización, `-u` filtrar por usuario.

![TOP](Capturas/top.png)

### HTOP
Muestra los procesos mediante una interfaz visual.

```bash
htop
htop -u usuario
```
Opciones: `-u` filtra por usuario, `F6` ordena procesos.

![HTOP](Capturas/htop.png)

### ATOP
Monitoriza CPU, RAM, discos y procesos.

```bash
sudo atop 2
sudo atop -m 2 5
```
Opciones: `-m` información de memoria, `-d` información de discos.

![ATOP](Capturas/atop.png)

## 2. Memoria RAM

### FREE
Muestra la memoria RAM y SWAP utilizada y disponible.

```bash
free -h
free -m
```
Opciones: `-h` unidades legibles, `-m` megabytes, `-s` actualizaciones periódicas.

![FREE](Capturas/free.png)

## 3. Almacenamiento

### DF
Muestra el espacio utilizado y disponible en las particiones.

```bash
df -h
df -hT
```
Opciones: `-h` tamaños legibles, `-T` tipo de sistema de archivos.

![DF](Capturas/df.png)

### DU
Muestra el espacio ocupado por archivos y carpetas.

```bash
du -sh ~
du -h --max-depth=1 ~
```
Opciones: `-s` muestra el total, `-h` tamaños legibles.

![DU](Capturas/du.png)

### IOSTAT
Analiza el rendimiento de los discos y la CPU.

```bash
iostat -xz 1 3
```
Opciones: `-x` estadísticas ampliadas, `-z` oculta dispositivos sin actividad.

![IOSTAT](Capturas/iostat.png)

## 4. Tráfico de red

### TCPDUMP
Captura y analiza paquetes de red.

```bash
sudo tcpdump -i lo -nn -c 8 icmp
```
Opciones: `-i` interfaz, `-nn` no resuelve nombres, `-c` número de paquetes.

![TCPDUMP](Capturas/tcpdump.png)

### TCPTRACK
Monitoriza las conexiones TCP activas.

```bash
sudo tcptrack -i enp0s3
```
Opciones: `-i` selecciona interfaz, `-r` mantiene conexiones cerradas en pantalla.

![TCPTRACK](Capturas/tcptrack.png)

### IPTRAF
Analiza el tráfico y las estadísticas de red.

```bash
sudo iptraf-ng
sudo iptraf-ng -g
```
Opciones: `-g` estadísticas generales, `-i` selecciona interfaz.

![IPTRAF](Capturas/iptraf.png)

### BMON
Muestra el tráfico de entrada y salida de la red.

```bash
bmon
bmon -p enp0s3
```
Opciones: `-p` selecciona las interfaces, `-r` intervalo de lectura.

![BMON](Capturas/bmon.png)

## 5. Puertos y conexiones

### SS
Muestra las conexiones y los puertos en escucha.

```bash
sudo ss -tulpen
```
Opciones: `-t` TCP, `-u` UDP, `-l` puertos en escucha, `-p` procesos, `-n` valores numéricos.

![SS](Capturas/ss.png)

### NMAP
Analiza equipos y detecta puertos abiertos.

```bash
nmap 127.0.0.1
nmap -p 80 127.0.0.1
```
Opciones: `-p` selecciona puertos, `-sV` identifica servicios y versiones.

![NMAP](Capturas/nmap.png)

## 6. Análisis de resultados

**1. ¿Cómo comprobarías la cantidad de memoria RAM disponible?**

Con `free -h`, consultando la columna available.

**2. ¿Qué diferencia existe entre df y du?**

`df` muestra el espacio disponible en particiones y `du` el espacio ocupado por archivos y carpetas.

**3. ¿Qué diferencias existen entre ss y nmap?**

`ss` muestra conexiones locales y `nmap` analiza puertos de equipos de la red.

**4. ¿Cómo comprobarías si un servidor tiene abierto el puerto 80?**

Con `nmap -p 80 DIRECCION_IP`.

**5. ¿Qué herramienta utilizarías para detectar un posible cuello de botella en el disco?**

`iostat`, porque muestra estadísticas de rendimiento y utilización del disco.

**6. ¿Por qué es importante monitorizar los recursos de un servidor?**

Para detectar problemas, prevenir fallos y mejorar el rendimiento del sistema.

## 7. Con
