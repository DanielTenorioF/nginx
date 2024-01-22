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

## C) Virtual Hosting

Nuestro servidor web ofrecera balanceo de carga desde https  a dos sitios web que tengan también https.

Crear el siguiente fichero de configuracion en /etc/nginx/conf.d/loadbalancer.conf y editarlo:

![image](/img/practica6.png)