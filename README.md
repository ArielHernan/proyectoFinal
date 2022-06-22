# RESERVAS, PROYECTO FIN DE CICLO
 ## El código de la aplicación se sencuentra en el siguiente repositorio:
https://github.com/ArielHernan/reservas

# APLICACIÓN DESPLEGADA 20/06/2022 :
http://proyectodaw.es/

# VIDEO TUTORIAL FUNCIONAMIENTO DE LA APLICACIÓN
https://www.youtube.com/watch?v=1zJHfOmq2qA

# DESCRIPCIÓN DE LA APLICACIÓN:

Se trata de una simple aplicación de reserva para un restaurante, 

# DESPLIEGUE
La aplicación va a tener un despliegue en un hosting de pago, en principio estaba programado en hostinger pero al final se realizará en https://mars.ignitionserver.net:2083/ , un hosting muy económico que he encontrado 
El dominio es:
(http://proyectodaw.es)
El hosting es de la empresa:
(https://mars.ignitionserver.net:2083/ )

# CUMPLIMIENTO DE ESPECIFICACIONES
- **CSS** :
- Creación de Landing page, animaciòn del color de fondo a través de css a código, creación en svg y presentación en todas las páginas del logo, inserción de video en el área de creación de reserva y background video en el área de modificación de la reserva.    
-                                                                  - -
- **PHP** :
- Realización de la página entera en el framework aprendido en el curso: LARAVEL, 
- Utilización de Tailwind css para los colores de la web, formularios, tablas.
- 
- **JAVASCRIPT :**
- Uso del javascript integrado en el framework Laravel.

# CHECKPOINT
He colgado el video de lo que llevo hecho en la siguiente dirección de youtube:
https://youtu.be/u3Sq216W0Lo


# FUNCIONAMIENTO Y FUNCIONES PARA EL USUARIO

## Aterrizaje en landing page
Una vez que aterrizamos en la Landing page, tendremos 2 opciones
-> **Logarse**
-> **Darse de alta** 

### Logarse:
#### Logarse como usuario:
Hay un botón donde puedes reservar mesa, al pinchar, accedes al formulario de login una vez comprobado tu usuario y contraseña puedes acceder a tu panel de reservas donde podrás ver las reservas realizadas, crear una reserva, modificar una reserva o anular una reserva.
#### Logarse como administrtador:
Las mismas funciones que el usuario normal,ya que el propietario del negocio puede hacer sus reservas como un usuario más pero además tiene una opción en el panel de reservas que se permite acceder a otra área, la de Gestión de reservas donde ver todas las reservas y desde ahí podrá confirmar, rechazar o borrar una reserva.

### Darse de alta: 
- Si no tienes cuenta puedes darte de alta fácilmente, esto se haría pinchando en el botón "darse de alta" aquí tienes 2 opciones,
-  **darse de alta como usuario o como administrador**.
- Para darse de alta como **administrador** lo único que hay que hacer es rellenar la contraseña previamente establecida y elegir la contraseña propia(no tienen que ser la misma) y al rellenar la contraseña preestablecida, entrarás en el panel de administración donde además de tener todas las opciones de un usuario normal tendrás las opciones de administrador que es la de gestionar reservas, es decir, se ven todas las reservas realizadas y además se pueden aceptar , rechazar o borrar las reservas.

- Par darse de alta como **usuario** lo único que tienes que hacer es rellenar los datos del formulario de alta y una vez completado accedes al panel de reservas, donde mirar las reservas que has realizado (anular, modificar) o realizar reserva nueva.


# TECNOLOGÍAS A USAR:

| Front-end | Back-end |
| ------------- | ------------- |
|CSS  | PHP  |
|TAILWIND | LARAVEL 8  |
|..     |   MYSQL |


>
- **En el back-end** usaré PHP con el framework Laravel8.
- **En el Front-End** usaré tailwind y css.
- **Gestor de Base de datos** será Mysql.


# MOCKUP
Se puede ver el mock up en teléfono móvil en el siguiente link:

https://www.figma.com/file/1xVG8hNWEBvW6hhTkIIkFV/Free-Clay-Mockups-(Community)?node-id=0%3A1

# Modelado de la base de datos:
- **El diseño del modelo E/R consta de 3 tablas**,
- una de USUARIO  
- otra de RESERVAS
- y una última de MESA.
- **La relación sería:**
Un usuario puede tener cero o muchas reservas, pero una reserva tiene que
tener obligatoriamente un usuario y sólo uno.
Una reserva puede tener una o muchas mesas y una mesa puede tener
ninguna o muchas reservas

# MODELADO FINAL DE LA BASE DE DATOS:

Este sería el modelado final de la base de datos, una vez hechas las migraciones y trabajado con Laravel:



![image](https://user-images.githubusercontent.com/72375204/168426260-9df76ceb-a94b-492e-b91d-706a77a93726.png)

# SQL FINAL BBDD
Una vez empezado a relizar la base de datos con las migraciones, y programar la aplicación he tenido que poner y quitar algunos campos 
para facilitar la programación y conducir la aplicación por el camino correcto hacia una Version Mínima Funcional, ya que es el objetivo real que puedo conseguir.



