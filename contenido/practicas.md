# Casos Practicos

## A) Version de Nginx instalados

- Para verificar la version de Nginx, ejecutar:

![image](/img/practica1.png)


## B) Ficheros de configuracion

Para ver los archivos de configuracion, situarse en /etc/nginx y ejecutar:

![image](/img/practica2.png)

- **/etc/nginx/nginx.conf:** Archivo de configuracion principal. Contiene las configuracion globales de todo el servidor.

- **/etc/nginx/conf.d/ y /etc/nginx/sites-available/:** Archivos de configuración específicos para cada sitio o aplicacion. Definen como se debe manejar el tráfico. Enlazados a **/etc/nginx/sites-enabled/** para activarlos.


## C) Página web por defecto

Modificar la página web que lanza por defecto y personalizarla:

- Editar el archivo index.html situado en /usr/share/nginx/html/index.html

![image](/img/practica3.png)

- Reiniciar el servicio nginx

![image](/img/practica4.png)

Resultado:

![image](/img/practica5.png)

## D) Virtual Hosting

Nuestro servidor web ofrecera balanceo de carga desde https a dos sitios web que tengan también https.

- **Balanceo de carga Nginx:** 172.26.2.5
- **Servidor de aplicación 1:** 172.26.2.205
- **Servidor de aplicación 2:** 172.26.2.55

Lo primero será definir el nombre de dominio modificando el fichero /etc/hosts:

![image](/img/practica14.png)

En el Servidor de Aplicacion 1, modificar el index.html por defecto en /var/www/html/ y crear uno nuevo:

![image](/img/practica6.png)

Hacer lo mismo en el Servidor de Aplicacion 2:

![image](/img/practica7.png)

En el Balanceador de Carga Nginx, eliminar el archivo de configuracion predeterminado y crear uno nuevo en /etc/nginx/conf.d/loadbalancer.conf

![image](/img/practica8.png)
![image](/img/practica9.png)

Verificar errores de sintaxis ejecutando:

![image](/img/practica10.png)

Por último, para aplicar los cambios, reiniciar el servicio.

![image](/img/practica11.png)

Para verificar el Balanceo de Carga Nginx, abrir el navegador web y acceder al servidor de equilibrio introduciendo en la URL http://**nombreDominio**.com.

En este caso seria http://**danielt**.com.

Primero se redirigira al Servidor de Aplicaciones 1:

![image](/img/practica12.png)

Actualizar la página repetidas veces, esto deberá de cargar la apliación desde el Servidor de Aplicaciones 2:

![image](/img/practica13.png)

### Balanceo de Carga https

Una vez compleado y verificado los apartados anteriores, en el Balanceador de Carga Nginx, comprobar si está instalado **openssl**:

![image](/img/practica15.png)

Una vez instalado, crear un certificado si no tenemos uno creado:

Ejecutar el siguiente comando:

![image](/img/practica16.png)

Darle a intro y aceptar para terminar:

![image](/img/practica17.png)

**Se crearan 2 archivos**

A continuación, crear el directorio certificados en /etc/nginx/ y mover los  

![image](/img/practica18.png)

Modificar el fichero /etc/nginx/conf.d/loadbalancer.conf:

![image](/img/practica19.png)

Reiniciar el servicio:

![image](/img/practica20.png)

### Resultado

En la URL del navegador, introducir https://**nombreDominio**.com.

En este caso seria https://**danielt**.com.

![image](/img/practica21.png)

![image](/img/practica22.png)