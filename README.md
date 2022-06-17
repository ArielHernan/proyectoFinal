# RESERVAS, PROYECTO FIN DE CICLO

https://github.com/ArielHernan/reservas

# DESCRIPCIÓN DE LA APLICACIÓN:

Se trata de una simple aplicación de reserva para un restaurante, 

# DESPLIEGUE
La aplicación va a tener un despliegue en un hosting de pago, en principio estaba programado en hostinger pero al final se realizará en https://mars.ignitionserver.net:2083/ , un hosting muy económico que he encontrado 
El dominio es:
(http://proyectodaw.es
El hosting es de la empresa:
(https://mars.ignitionserver.net:2083/ )

# CHECKPOINT
He colgado el video de lo que llevo hecho en la siguiente dirección de youtube:

https://youtu.be/u3Sq216W0Lo

# FUNCIONAMMIENTO Y FUNCIONES PARA EL USUARIO

## Aterrizaje en landing page
Una vez que aterrizamos en la Landing page, tendremos 2 opciones
-> **Logarse**
-> **Darse de alta** 

**Logarse**: Hay un botón donde puedes reservar mesa, al pinchar, accedes al formulario de login una vez comprobado tu usuario y contraseña puedes acceder a tu panel de reservas donde podrás ver las reservas realizadas, anular tus reservas, modificar tus reservas o anular tus reservas.

**Darse de alta**: si no tienes cuenta puedes darte de alta fácilmente, esto se haría pinchando en el botón "darse de alta" aquí tienes 2 opciones, **darse de alta como usuario o como administrador**.
Para darse de alta como **administrador** lo único que hay que hacer es rellenar la contraseña previamente establecida y elegir la contraseña propia(no tienen que ser la misma) y al rellenar la contraseña preestablecida, entrarás en el panel de administración donde además de tener todas las opciones de un usuario normal tendrás las opciones de administrador que es la de gestionar reservas, es decir, se ven todas las reservas realizadas y además se pueden aceptar , rechazar o borrar las reservas.

Par darse de alta como **usuario** lo único que tienes que hacer es rellenar los datos del formulario de alta y una vez completado accedes al panel de reservas, donde mirar las reservas que has realizado (anular, modificar) o realizar reserva nueva.

# Modelado de la base de datos:
El diseño del modelo E/R consta de 3 tablas, una de USUARIO otra de
RESERVAS y una última de MESA.
La relación sería:
Un usuario puede tener cero o muchas reservas, pero una reserva tiene que
tener obligatoriamente un usuario y sólo uno.
Una reserva puede tener una o muchas mesas y una mesa puede tener
ninguna o muchas reservas

# MODELADO FINAL DE LA BASE DE DATOS:

Este sería el modelado final de la base de datos, una vez hechas las migraciones y trabajado con Laravel:



![image](https://user-images.githubusercontent.com/72375204/168426260-9df76ceb-a94b-492e-b91d-706a77a93726.png)

# SQL FINAL base de datos
Una vez empezado a relizar la base de datos con las migraciones, y programar la aplicación he tenido que poner y quitar algunos campos 
para facilitar la programación y conducir la aplicación por el camino correcto hacia una Version Mínima Funcional, ya que es el objetivo real que puedo conseguir.

phpMyAdmin SQL Dump
version 5.1.1
https://www.phpmyadmin.net/
Servidor: 127.0.0.1
Tiempo de generación: 10-06-2022 a las 00:51:31
versión del servidor: 10.4.22-MariaDB
Versión de PHP: 8.1.2

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
START TRANSACTION;
SET time_zone = "+00:00";


40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
40101 SET NAMES utf8mb4 */;


Base de datos: `reservas`
 Estructura de tabla para la tabla `failed_jobs`

CREATE TABLE `failed_jobs` (
  `id` bigint(20) UNSIGNED NOT NULL,
  `uuid` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `connection` text COLLATE utf8mb4_unicode_ci NOT NULL,
  `queue` text COLLATE utf8mb4_unicode_ci NOT NULL,
  `payload` longtext COLLATE utf8mb4_unicode_ci NOT NULL,
  `exception` longtext COLLATE utf8mb4_unicode_ci NOT NULL,
  `failed_at` timestamp NOT NULL DEFAULT current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

 Estructura de tabla para la tabla `mesas`


CREATE TABLE `mesas` (
  `numero_mesa` int(10) UNSIGNED NOT NULL,
  `numero_comensales` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;


 Estructura de tabla para la tabla `migrations`

CREATE TABLE `migrations` (
  `id` int(10) UNSIGNED NOT NULL,
  `migration` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `batch` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;


Volcado de datos para la tabla `migrations`

INSERT INTO `migrations` (`id`, `migration`, `batch`) VALUES
(1, '2014_10_12_000000_create_users_table', 1),
(2, '2014_10_12_100000_create_password_resets_table', 1),
(3, '2019_08_19_000000_create_failed_jobs_table', 1),
(4, '2019_12_14_000001_create_personal_access_tokens_table', 1),
(5, '2022_05_27_000002_create_usuario_table', 1),
(6, '2022_05_27_153433_create_reservas_table', 1),
(7, '2022_05_27_153623_create_mesas_table', 1),
(8, '2022_05_27_153654_create_reservas_mesas_table', 1);

Estructura de tabla para la tabla `password_resets`

CREATE TABLE `password_resets` (
  `email` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `token` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

 Estructura de tabla para la tabla `personal_access_tokens`

CREATE TABLE `personal_access_tokens` (
  `id` bigint(20) UNSIGNED NOT NULL,
  `tokenable_type` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `tokenable_id` bigint(20) UNSIGNED NOT NULL,
  `name` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `token` varchar(64) COLLATE utf8mb4_unicode_ci NOT NULL,
  `abilities` text COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `last_used_at` timestamp NULL DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;


 Estructura de tabla para la tabla `reservas`

CREATE TABLE `reservas` (
  `id_reserva` int(10) UNSIGNED NOT NULL,
  `id_usuario` int(10) UNSIGNED NOT NULL,
  `estado` int(11) NOT NULL,
  `fecha_hora_inicio` datetime(2) NOT NULL,
  `fecha_hora_fin` datetime(2) NOT NULL,
  `numero_personas` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

Volcado de datos para la tabla `reservas`

INSERT INTO `reservas` (`id_reserva`, `id_usuario`, `estado`, `fecha_hora_inicio`, `fecha_hora_fin`, `numero_personas`) VALUES
(7, 1, 2, '2022-06-21 02:04:00.00', '2022-06-21 02:04:00.00', 100),
(8, 1, 2, '2022-06-30 00:00:00.00', '2022-06-30 00:00:00.00', 500),
(10, 10, 2, '2022-06-22 22:22:00.00', '2022-06-22 22:22:00.00', 22),
(11, 13, 1, '2022-06-30 22:22:00.00', '2022-06-30 22:22:00.00', 100),
(12, 13, 1, '2022-06-28 04:44:00.00', '2022-06-28 04:44:00.00', 4),
(13, 10, 1, '0002-02-22 22:22:00.00', '0002-02-22 22:22:00.00', 22),
(34, 14, 1, '1202-02-21 21:21:00.00', '1202-02-21 21:21:00.00', 21),
(35, 1, 0, '2003-03-31 17:45:00.00', '2003-03-31 17:45:00.00', 3),
(36, 1, 0, '2002-02-02 17:08:00.00', '2002-02-02 17:08:00.00', 3),
(37, 1, 0, '2021-02-21 18:48:00.00', '2021-02-21 18:48:00.00', 2000),
(38, 1, 0, '2021-02-21 18:48:00.00', '2021-02-21 18:48:00.00', 2000),
(39, 1, 0, '2021-02-21 18:48:00.00', '2021-02-21 18:48:00.00', 2000),
(40, 1, 0, '2022-03-22 18:48:00.00', '2022-03-22 18:48:00.00', 3000),
(41, 1, 0, '2022-03-22 18:48:00.00', '2022-03-22 18:48:00.00', 3000),
(42, 1, 0, '2022-03-22 18:48:00.00', '2022-03-22 18:48:00.00', 3000),
(43, 1, 0, '2022-03-22 18:48:00.00', '2022-03-22 18:48:00.00', 3000),
(44, 1, 0, '2022-03-22 18:48:00.00', '2022-03-22 18:48:00.00', 3000),
(45, 1, 0, '2022-03-22 18:48:00.00', '2022-03-22 18:48:00.00', 3000),
(46, 1, 0, '2022-03-22 18:48:00.00', '2022-03-22 18:48:00.00', 3000),
(47, 1, 0, '2022-06-15 02:48:00.00', '2022-06-15 02:48:00.00', 1000);

 Estructura de tabla para la tabla `reservas_mesas`

CREATE TABLE `reservas_mesas` (
  `id_reserva` int(10) UNSIGNED NOT NULL,
  `numero_mesa` int(10) UNSIGNED NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

Estructura de tabla para la tabla `users`

CREATE TABLE `users` (
  `id_usuario` int(10) UNSIGNED NOT NULL,
  `name` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `email` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `email_verified_at` timestamp NULL DEFAULT NULL,
  `password` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `telefono` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `remember_token` varchar(100) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL,
  `perfilUser` int(11) NOT NULL DEFAULT 1
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

Estructura de tabla para la tabla `usuario`


CREATE TABLE `usuario` (
  `id_usuario` int(10) UNSIGNED NOT NULL,
  `name` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `email` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `email_verified_at` timestamp NULL DEFAULT NULL,
  `password` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `telefono` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `remember_token` varchar(100) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL,
  `perfilUser` int(11) NOT NULL DEFAULT 1
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

 Volcado de datos para la tabla `usuario`

INSERT INTO `usuario` (`id_usuario`, `name`, `email`, `email_verified_at`, `password`, `telefono`, `remember_token`, `created_at`, `updated_at`, `perfilUser`) VALUES
(1, 'ariel', 'a@gmail.com', NULL, '$2y$10$mNGrZ87HrHfZ7xwA0yfBBu5y89R9W5sy.BtV0vSmLNi15Vx4cPPkC', '1', NULL, '2022-05-30 13:46:14', '2022-05-30 13:46:14', 2),
(10, 'qwe', 'pepe6@gmail.com', NULL, '$2y$10$w8Wr7h0jsXB.a0/0kSY3LOkh2QUYOV7iZ7.HPqPCV3eNwKGEcxaTO', '12', NULL, '2022-05-30 14:30:52', '2022-05-30 14:30:52', 0),
(11, 'qwe', 'pepe7@gmail.com', NULL, '$2y$10$yg5dW7zls9Rkmc6kLJM6S.ikHRU4PwdtBw/nGocBJKIaGPwx376D.', '12', NULL, '2022-05-30 14:32:05', '2022-05-30 14:32:05', 0),
(12, 'pepe9', 'aeeee@gmail.com', NULL, '$2y$10$loVR7GrNzD.AWDuMmuy6b.pzQTOgBldJtdnFqRF5.TmIn5qkbIw0.', '12345678', NULL, '2022-05-30 14:32:55', '2022-05-30 14:32:55', 2),
(13, 'aaaa', 'b@gmail.com', NULL, '$2y$10$PJVNRCrjxBL5TAeuLusfCOLtQ4CKXcoWLSjZD6PBasLsXcghfPTze', '33', NULL, '2022-05-30 15:11:12', '2022-05-30 15:11:12', 0),
(14, 'ariel', 'arielrojass@hotmail.com', NULL, '$2y$10$Y5yYcOjMrX2am1JD.fDmX.BSptdCT8.t.0rwylRDJX9Zp4TOa/Sra', '666666666', NULL, '2022-06-05 12:24:21', '2022-06-05 12:24:21', 0),
(15, 'z', 'z@gmail.com', NULL, '$2y$10$VD/rgtK.eBAlz32PRGmE9uVMjnXQo6zVsVneuPTzO.XQMkmf9JOUu', '666666666', NULL, '2022-06-06 13:12:44', '2022-06-06 13:12:44', 2),
(16, 'y', 'y@gmail.com', NULL, '$2y$10$AQECJGjGQi25DZ2KOjFBkeQBcG8eEXa/l57d37HO0SK3hfduuyOf.', '555555555', NULL, '2022-06-06 13:13:41', '2022-06-06 13:13:41', 0);

 Índices para tablas volcadas

 Indices de la tabla `failed_jobs`

ALTER TABLE `failed_jobs`
  ADD PRIMARY KEY (`id`),
  ADD UNIQUE KEY `failed_jobs_uuid_unique` (`uuid`);

 Indices de la tabla `mesas`

ALTER TABLE `mesas`
  ADD PRIMARY KEY (`numero_mesa`);

 Indices de la tabla `migrations`

ALTER TABLE `migrations`
  ADD PRIMARY KEY (`id`);

 Indices de la tabla `password_resets`

ALTER TABLE `password_resets`
  ADD KEY `password_resets_email_index` (`email`);

 Indices de la tabla `personal_access_tokens`

ALTER TABLE `personal_access_tokens`
  ADD PRIMARY KEY (`id`),
  ADD UNIQUE KEY `personal_access_tokens_token_unique` (`token`),
  ADD KEY `personal_access_tokens_tokenable_type_tokenable_id_index` (`tokenable_type`,`tokenable_id`);

 Indices de la tabla `reservas`


ALTER TABLE `reservas`
  ADD PRIMARY KEY (`id_reserva`),
  ADD KEY `reservas_id_usuario_foreign` (`id_usuario`);

 Indices de la tabla `reservas_mesas`

ALTER TABLE `reservas_mesas`
  ADD KEY `reservas_mesas_id_reserva_foreign` (`id_reserva`),
  ADD KEY `reservas_mesas_numero_mesa_foreign` (`numero_mesa`);


 Indices de la tabla `users`

ALTER TABLE `users`
  ADD PRIMARY KEY (`id_usuario`),
  ADD UNIQUE KEY `users_email_unique` (`email`);

 Indices de la tabla `usuario`

ALTER TABLE `usuario`
  ADD PRIMARY KEY (`id_usuario`),
  ADD UNIQUE KEY `usuario_email_unique` (`email`);

 AUTO_INCREMENT de las tablas volcadas

 AUTO_INCREMENT de la tabla `failed_jobs`

ALTER TABLE `failed_jobs`
  MODIFY `id` bigint(20) UNSIGNED NOT NULL AUTO_INCREMENT;

 AUTO_INCREMENT de la tabla `mesas`

ALTER TABLE `mesas`
  MODIFY `numero_mesa` int(10) UNSIGNED NOT NULL AUTO_INCREMENT;

 AUTO_INCREMENT de la tabla `migrations`

ALTER TABLE `migrations`
  MODIFY `id` int(10) UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=9;

 AUTO_INCREMENT de la tabla `personal_access_tokens`

ALTER TABLE `personal_access_tokens`
  MODIFY `id` bigint(20) UNSIGNED NOT NULL AUTO_INCREMENT;

 AUTO_INCREMENT de la tabla `reservas`

ALTER TABLE `reservas`
  MODIFY `id_reserva` int(10) UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=48;

 AUTO_INCREMENT de la tabla `users`

ALTER TABLE `users`
  MODIFY `id_usuario` int(10) UNSIGNED NOT NULL AUTO_INCREMENT;

 AUTO_INCREMENT de la tabla `usuario`

ALTER TABLE `usuario`
  MODIFY `id_usuario` int(10) UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=17;


Restricciones para tablas volcadas



Filtros para la tabla `reservas`

ALTER TABLE `reservas`
  ADD CONSTRAINT `reservas_id_usuario_foreign` FOREIGN KEY (`id_usuario`) REFERENCES `usuario` (`id_usuario`) ON DELETE CASCADE;


 Filtros para la tabla `reservas_mesas`

ALTER TABLE `reservas_mesas`
  ADD CONSTRAINT `reservas_mesas_id_reserva_foreign` FOREIGN KEY (`id_reserva`) REFERENCES `reservas` (`id_reserva`) ON DELETE CASCADE,
  ADD CONSTRAINT `reservas_mesas_numero_mesa_foreign` FOREIGN KEY (`numero_mesa`) REFERENCES `mesas` (`numero_mesa`) ON DELETE CASCADE;
COMMIT;

40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;


# TECNOLOGÍAS A USAR:

| Front-end | Back-end |
| ------------- | ------------- |
|CSS  | PHP  |
|TAILWIND | LARAVEL 8  |
|..     |   MYSQL |

En el backend usaré PHP con el framework Laravel8
En el Front End usaré tailwind o bootstrap Y css
Gestor de Base de datos será Mysql



![image](https://user-images.githubusercontent.com/72375204/174285174-45fa81e1-5f7b-47ff-8a8e-4bffada7507f.png)

# MOCKUP
Se puede ver el mock up en teléfono móvil en el siguiente link:

https://www.figma.com/file/1xVG8hNWEBvW6hhTkIIkFV/Free-Clay-Mockups-(Community)?node-id=0%3A1
