# RESERVAS

# DESCRIPCIÓN DE LA APLICACIÓN:

Se trata de una simple aplicación de reserva para un restaurante, 

a diferencia de una aplicación genérica, que valdría para todos los restaurantes, esta app pretende poder ser fácilmente personalizable para dar solución a restaurantes con una elevada relación calidad-precio (sector del lujo), locales que tienen que atender reservas fuera de horas de trabajo ya que su público objetivo está acostumbrado a esa rutina, reservas que de no ser atendidas cuando el cliente llama se perderían, el objetivo es poder captar todas las reservas sin que ningún camarero o manager ocupe horas fuera de su horario laboral para estas tareas y solo se coja el tf en horario laboral.


# TECNOLOGÍAS A USAR:
En el backend usaré PHP con el framework Laravel8
En el Front End usaré tailwind o bootstrap
Gestor de Base de datos será Mysql

# Modelado de la base de datos:
El diseño del modelo E/R consta de 3 tablas, una de USUARIO otra de
RESERVAS y una última de MESA.
La relación sería:
Un usuario puede tener cero o muchas reservas, pero una reserva tiene que
tener obligatoriamente un usuario y sólo uno.
Una reserva puede tener una o muchas mesas y una mesa puede tener
ninguna o muchas reservas

![esquemaModeloER](https://user-images.githubusercontent.com/72375204/161590306-85cbb4d1-8e66-4268-909c-e0b0565a77da.png)

# MOCKUP
<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2F1xVG8hNWEBvW6hhTkIIkFV%2FFree-Clay-Mockups-(Community)%3Fnode-id%3D0%253A1" allowfullscreen></iframe>
