![image](/img/comparacion.jpg)


## ¿Que diferencia hay con Apache?

Las principales diferencias en el funcionamiento entre Apache y Nginx son:

**Manejo de Hilos:**
- Apache requiere abrir múltiples hilos para atender peticiones, mientras que Nginx puede manejar múltiples solicitudes con un solo hilo, lo que reduce el consumo de recursos y mejora la velocidad de respuesta.

**Concurrencia y Eficiencia:**
- Nginx es altamente eficiente en situaciones de alta carga, manejando peticiones de manera concurrente y asíncrona, a diferencia de Apache, que puede tener dificultades en estas condiciones.

**Ejecución de PHP:**
- En Apache, es posible ejecutar PHP directamente en el servidor web, mientras que en Nginx se prefiere externalizarlo, siendo más eficiente. Se desaconseja el uso de mod_php en favor de PHP-FPM.

**Servicio de Contenido Estático:**
- Nginx destaca en la eficiente entrega de contenido estático (imágenes, PDF, CSS, Javascript), consumiendo menos recursos en comparación con Apache, que tiende a ser más lento en este aspecto.

**Funcionalidad como Proxy Inverso:**
- Nginx puede funcionar tanto como servidor HTTP como un proxy inverso, permitiendo una mayor flexibilidad en la configuración y distribución de carga. En contraste, Apache está más limitado a funcionar como servidor web.

