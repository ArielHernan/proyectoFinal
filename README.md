# RESERVAS
# checkpoint
He colgado el video de lo aue llevo hecho en la siguiente dirección de youtube:

https://youtu.be/u3Sq216W0Lo


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

![image](https://user-images.githubusercontent.com/72375204/164253076-69ce8b96-3db4-4651-a27c-edf863b7070d.png)


![esquemaModeloER](https://user-images.githubusercontent.com/72375204/161590306-85cbb4d1-8e66-4268-909c-e0b0565a77da.png)

LA programación de la base de datos, todavía pendiente de testear sería algo así:


CREATE TABLE usuario
(
  nombreUsuario VARCHAR(100) NOT NULL,
  Telefono VARCHAR(15) NOT NULL,
  password VARCHAR(15) NOT NULL,
  email VARCHAR(100) NOT NULL,
  PRIMARY KEY (email)
);

CREATE TABLE mesas
(
  numero_mesa INT NOT NULL,
  num_comensales INT NOT NULL,
  PRIMARY KEY (numero_mesa)
);

CREATE TABLE reserva
(
  num_reserva INT NOT NULL AUTO_INCREMENT,
  hora_reserva DATE NOT NULL,
  hora_fin_reserva DATE NOT NULL,
  numero_personas INT NOT NULL,
  email VARCHAR(100) NOT NULL,
  numero_mesa INT NOT NULL,
  PRIMARY KEY (num_reserva),
  FOREIGN KEY (email) REFERENCES usuario(email)
);

CREATE TABLE relationship
(
  num_reserva INT NOT NULL,
  numero_mesa INT NOT NULL,
  PRIMARY KEY (num_reserva, numero_mesa),
  FOREIGN KEY (num_reserva) REFERENCES reserva(num_reserva),
  FOREIGN KEY (numero_mesa) REFERENCES mesas(numero_mesa)
);


# MOCKUP
Se puede ver el mock up en teléfono móvil en el siguiente link:

https://www.figma.com/file/1xVG8hNWEBvW6hhTkIIkFV/Free-Clay-Mockups-(Community)?node-id=0%3A1
