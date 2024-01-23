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

Nuestro servidor web ofrecera balanceo de carga desde https a dos sitios web que tengan también https.

- **Balanceo de carga Nginx:** 172.26.2.5
- **Servidor de aplicación 1:** 172.26.2.205
- **Servidor de aplicación 2:** 172.26.2.55

Crear el siguiente fichero de configuracion en /etc/nginx/conf.d/loadbalancer.conf y editarlo:

![image](/img/practica6.png)

En el Servidor de Aplicacion 1, eliminar el archivo index.html por defecto en /usr/share/nginx/html/ y crear uno nuevo:

![image](/img/practica6.png)
![image](/img/practica7.png)

Hacer lo mismo en el Servidor de Aplicacion 2:

![image](/img/practica8.png)
![image](/img/practica9.png)

En el Balanceador de Carga Nginx, eliminar el archivo de configuracion predeterminado y crear uno nuevo en /etc/nginx/conf.d/load-balancing.conf

![image](/img/practica10.png)
![image](/img/practica11.png)

Verificar errores de sintaxis ejecutando:

![image](/img/practica12.png)

Por último, para aplicar los cambios, reiniciar el servicio.

![image](/img/practica13.png)