# Instalacion Nginx en Debian/Ubuntu

## PASO 1: Actualizar e Instalar

Actualizar la lista de paquetes:

- sudo apt update

Y posteriormente instalar Nginx:

- sudo apt install nginx

![image](/img/instalacion1.png)

## PASO 2: Iniciar y Habiliar Nginx

Iniciar el servicio Nginx

- sudo systemctl start nginx

Y por último habilitarlo:

- sudo systemctl enable nginx

![image](/img/instalacion2.png)

## Comprobar

En la URL del navegador, introducir la IP

![image](/img/instalacion3.png)