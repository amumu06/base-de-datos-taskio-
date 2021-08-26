# base-de-datos-taskio-
base de datos de proyeto
usuario 
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

tareas 
CREATE TABLE `tareas` (
	`tarea_id` INT(11) NOT NULL AUTO_INCREMENT,
	`fecha_planeacion` DATE NOT NULL,
	`fecha_ejecucion` DATE NULL DEFAULT NULL,
	`descripcion` VARCHAR(300) NOT NULL COLLATE 'utf8_general_ci',
	`usuario_crea_id` INT(11) NOT NULL,
	`usuario_asigna_id` INT(11) NULL DEFAULT NULL,
	PRIMARY KEY (`tarea_id`) USING BTREE,
	INDEX `fk_tareas_usrcreaid_idx` (`usuario_crea_id`) USING BTREE,
	INDEX `fk_tareas_usrasignaid_idx` (`usuario_asigna_id`) USING BTREE,
	CONSTRAINT `fk_tareas_usrasignaid` FOREIGN KEY (`usuario_asigna_id`) REFERENCES `db_taskio`.`usuario` (`usuario_id`) ON UPDATE CASCADE ON DELETE NO ACTION,
	CONSTRAINT `fk_tareas_usrcreaid` FOREIGN KEY (`usuario_crea_id`) REFERENCES `db_taskio`.`usuario` (`usuario_id`) ON UPDATE NO ACTION ON DELETE NO ACTION
)
COLLATE='utf8_general_ci'
ENGINE=InnoDB
;

