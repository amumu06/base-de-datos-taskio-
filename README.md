# base-de-datos-taskio-
base de datos de proyeto
CREATE TABLE `usuario` (
	`usuario_id` INT(11) NOT NULL AUTO_INCREMENT,
	`usuario` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8_general_ci',
	`nombre` VARCHAR(255) NULL DEFAULT NULL COLLATE 'utf8_general_ci',
	`apellido_paterno` VARCHAR(255) NULL DEFAULT NULL COLLATE 'utf8_general_ci',
	`apellido_materno` VARCHAR(255) NULL DEFAULT NULL COLLATE 'utf8_general_ci',
	`email` VARCHAR(255) NULL DEFAULT NULL COLLATE 'utf8_general_ci',
	`fecha_validacion` DATE NULL DEFAULT NULL,
	`contrasena` VARCHAR(300) NULL DEFAULT NULL COLLATE 'utf8_general_ci',
	PRIMARY KEY (`usuario_id`) USING BTREE
)
COLLATE='utf8_general_ci'
ENGINE=InnoDB
;
