# RESERVAS, PROYECTO FIN DE CICLO

# DESPLIEGUE
La aplicación va a tener un despliegue en un hosting de pago, donde actualmente se encuentra desplegado un proyecto anterior pero voy a 
reutilizarlo. 
El dominio es:
(http://proyectodaw.es
El hosting es de la empresa:
https://www.hostinger.es/

# CHECKPOINT
He colgado el video de lo que llevo hecho en la siguiente dirección de youtube:

https://youtu.be/u3Sq216W0Lo

# UPDATE BBDD:

Este sería el modelado final de la base de datos, una vez hechas las migraciones y trabajado con Laravel:


![image](https://user-images.githubusercontent.com/72375204/168426260-9df76ceb-a94b-492e-b91d-706a77a93726.png)

# nuevo sql base de datos
Una vez empezado a relizar la base de datos con las migraciones, y programar la aplicación he tenido que poner y quitar algunos campos 
para facilitar la programación y conducir la aplicación por el camino correcto hacia una Version Mínima Funcional, ya que es el objetivo real que puedo conseguir.

-- Base de datos: `reservas`
--

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `failed_jobs`
--

CREATE TABLE `failed_jobs` (
  `id` bigint(20) UNSIGNED NOT NULL,
  `uuid` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `connection` text COLLATE utf8mb4_unicode_ci NOT NULL,
  `queue` text COLLATE utf8mb4_unicode_ci NOT NULL,
  `payload` longtext COLLATE utf8mb4_unicode_ci NOT NULL,
  `exception` longtext COLLATE utf8mb4_unicode_ci NOT NULL,
  `failed_at` timestamp NOT NULL DEFAULT current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `mesas`
--

CREATE TABLE `mesas` (
  `numero_mesa` int(11) NOT NULL,
  `numero_comensales` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_spanish_ci;

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `migrations`
--

CREATE TABLE `migrations` (
  `id` int(10) UNSIGNED NOT NULL,
  `migration` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `batch` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Volcado de datos para la tabla `migrations`
--

INSERT INTO `migrations` (`id`, `migration`, `batch`) VALUES
(1, '2014_10_12_000000_create_users_table', 1),
(2, '2014_10_12_100000_create_password_resets_table', 1),
(3, '2019_08_19_000000_create_failed_jobs_table', 1),
(4, '2019_12_14_000001_create_personal_access_tokens_table', 1),
(6, '2022_05_06_145946_add_user_field', 2);

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `password_resets`
--

CREATE TABLE `password_resets` (
  `email` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `token` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `personal_access_tokens`
--

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

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `reservas`
--

CREATE TABLE `reservas` (
  `id_reserva` int(11) NOT NULL,
  `id_usuario` bigint(20) UNSIGNED NOT NULL,
  `estado` int(11) NOT NULL COMMENT '0-pendiente 1-aceptada 2-cancelada 3-rechazada',
  `fecha_hora_inicio` datetime NOT NULL,
  `fecha_hora_fin` datetime NOT NULL,
  `numero_personas` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_spanish_ci;

--
-- Volcado de datos para la tabla `reservas`
--

INSERT INTO `reservas` (`id_reserva`, `id_usuario`, `estado`, `fecha_hora_inicio`, `fecha_hora_fin`, `numero_personas`) VALUES
(1, 2, 1, '2022-05-13 16:50:44', '2022-05-13 16:50:44', 3),
(2, 2, 0, '2022-05-13 17:07:43', '2022-05-13 17:07:43', 14),
(3, 2, 0, '2022-05-13 17:17:40', '2022-05-13 17:17:40', 20),
(4, 2, 0, '2022-05-13 18:17:43', '2022-05-13 18:17:43', 34),
(5, 2, 0, '2022-05-13 18:35:41', '2022-05-13 18:35:41', 72);

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `reservas_mesas`
--

CREATE TABLE `reservas_mesas` (
  `numero_mesa` int(11) NOT NULL,
  `numero_reserva` int(11) NOT NULL,
  `asistentes` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_spanish_ci;

-- --------------------------------------------------------

--
-- Estructura de tabla para la tabla `users`
--

CREATE TABLE `users` (
  `id` bigint(20) UNSIGNED NOT NULL,
  `name` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `email` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `email_verified_at` timestamp NULL DEFAULT NULL,
  `password` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `telefono` varchar(255) COLLATE utf8_spanish_ci NOT NULL,
  `remember_token` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_spanish_ci;

--
-- Volcado de datos para la tabla `users`
--

INSERT INTO `users` (`id`, `name`, `email`, `email_verified_at`, `password`, `telefono`, `remember_token`, `created_at`, `updated_at`) VALUES
(2, 'ariel', 'prueba@gmail.com', NULL, '$2y$10$NwGWWzfToYP5J8dv//AnfeT0eqTxBtgiklSdXe/2Ds2tOubEI5VNC', '666666666', NULL, '2022-05-06 13:54:19', '2022-05-06 13:54:19'),
(3, 'pepe', 'pepe@gmail.com', NULL, '$2y$10$BdpzUbOUG/K0wi3cO/CgEO5pvrVu7WKDLpNtFdrshJkzIEXxNM0sa', '666666666', NULL, '2022-05-13 16:37:33', '2022-05-13 16:37:33');

--
-- Índices para tablas volcadas
--

--
-- Indices de la tabla `failed_jobs`
--
ALTER TABLE `failed_jobs`
  ADD PRIMARY KEY (`id`),
  ADD UNIQUE KEY `failed_jobs_uuid_unique` (`uuid`);

--
-- Indices de la tabla `mesas`
--
ALTER TABLE `mesas`
  ADD PRIMARY KEY (`numero_mesa`);

--
-- Indices de la tabla `migrations`
--
ALTER TABLE `migrations`
  ADD PRIMARY KEY (`id`);

--
-- Indices de la tabla `password_resets`
--
ALTER TABLE `password_resets`
  ADD KEY `password_resets_email_index` (`email`);

--
-- Indices de la tabla `personal_access_tokens`
--
ALTER TABLE `personal_access_tokens`
  ADD PRIMARY KEY (`id`),
  ADD UNIQUE KEY `personal_access_tokens_token_unique` (`token`),
  ADD KEY `personal_access_tokens_tokenable_type_tokenable_id_index` (`tokenable_type`,`tokenable_id`);

--
-- Indices de la tabla `reservas`
--
ALTER TABLE `reservas`
  ADD PRIMARY KEY (`id_reserva`),
  ADD KEY `id_usuario` (`id_usuario`);

--
-- Indices de la tabla `reservas_mesas`
--
ALTER TABLE `reservas_mesas`
  ADD PRIMARY KEY (`numero_mesa`,`numero_reserva`),
  ADD KEY `numero_reserva` (`numero_reserva`);

--
-- Indices de la tabla `users`
--
ALTER TABLE `users`
  ADD PRIMARY KEY (`id`),
  ADD UNIQUE KEY `users_email_unique` (`email`);

--
-- AUTO_INCREMENT de las tablas volcadas
--

--
-- AUTO_INCREMENT de la tabla `failed_jobs`
--
ALTER TABLE `failed_jobs`
  MODIFY `id` bigint(20) UNSIGNED NOT NULL AUTO_INCREMENT;

--
-- AUTO_INCREMENT de la tabla `migrations`
--
ALTER TABLE `migrations`
  MODIFY `id` int(10) UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=7;

--
-- AUTO_INCREMENT de la tabla `personal_access_tokens`
--
ALTER TABLE `personal_access_tokens`
  MODIFY `id` bigint(20) UNSIGNED NOT NULL AUTO_INCREMENT;

--
-- AUTO_INCREMENT de la tabla `reservas`
--
ALTER TABLE `reservas`
  MODIFY `id_reserva` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=6;

--
-- AUTO_INCREMENT de la tabla `users`
--
ALTER TABLE `users`
  MODIFY `id` bigint(20) UNSIGNED NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=4;

--
-- Restricciones para tablas volcadas
--

--
-- Filtros para la tabla `reservas`
--
ALTER TABLE `reservas`
  ADD CONSTRAINT `reserva_usuario` FOREIGN KEY (`id_usuario`) REFERENCES `users` (`id`);

--
-- Filtros para la tabla `reservas_mesas`
--
ALTER TABLE `reservas_mesas`
  ADD CONSTRAINT `numero_mesa` FOREIGN KEY (`numero_mesa`) REFERENCES `mesas` (`numero_mesa`) ON DELETE CASCADE ON UPDATE CASCADE,
  ADD CONSTRAINT `numero_reserva` FOREIGN KEY (`numero_reserva`) REFERENCES `reservas` (`id_reserva`) ON DELETE CASCADE ON UPDATE CASCADE;
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;


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
