

# Análisis del Código SQL

## 1. Selección de la Base de Datos
```sql
USE Pvz;
Descripción: Selecciona la base de datos Pvz para realizar operaciones posteriores.

2. Creación de la Tabla Usuario
sql
CREATE TABLE Usuario (
    Nombre VARCHAR(20) PRIMARY KEY,
    Contraseña VARCHAR(255) NOT NULL,
    Imagen LONGBLOB,
    esAdmin BOOLEAN DEFAULT FALSE
);
Descripción: Crea una tabla llamada Usuario con las siguientes columnas:

Nombre: Clave primaria de tipo VARCHAR(20).

Contraseña: Campo obligatorio de tipo VARCHAR(255).

Imagen: Campo de tipo LONGBLOB para almacenar imágenes.

esAdmin: Campo booleano con valor por defecto FALSE.

3. Consulta de Todos los Usuarios
sql

SELECT * FROM USUARIO;
Descripción: Realiza una consulta para obtener todos los registros de la tabla Usuario.

4. Eliminación del Procedimiento validacion_usuario
sql

DROP PROCEDURE validacion_usuario;
Descripción: Elimina el procedimiento almacenado validacion_usuario si existe.

5. Creación del Procedimiento validacion_usuario
sql

DELIMITER //
CREATE PROCEDURE validacion_usuario(Nombre_User varchar(20), Contraseña_user varchar(255))
BEGIN
    SELECT *
    FROM Usuario
    WHERE Nombre = Nombre_User
      AND Contraseña = Contraseña_user;
END //
DELIMITER ;
Descripción: Crea un procedimiento almacenado llamado validacion_usuario que:

Recibe dos parámetros: Nombre_User y Contraseña_user.

Realiza una consulta para seleccionar todos los campos de la tabla Usuario donde el Nombre y la Contraseña coincidan con los parámetros proporcionados.

6. Eliminación del Procedimiento obtener_admin

Copy
DROP PROCEDURE obtener_admin;
Descripción: Elimina el procedimiento almacenado obtener_admin si existe.

7. Creación del Procedimiento obtener_admin


DELIMITER //
CREATE PROCEDURE obtener_admin(Nombre_User varchar(20), Contraseña_user varchar(255))
BEGIN
    SELECT CASE WHEN esAdmin = 1 THEN 1 ELSE 0 END AS esAdmin
    FROM Usuario
    WHERE Nombre = Nombre_User
      AND Contraseña = Contraseña_user;
END //
DELIMITER ;
Descripción: Crea un procedimiento almacenado llamado obtener_admin que:

Recibe dos parámetros: Nombre_User y Contraseña_user.

Realiza una consulta para determinar si el usuario es administrador (esAdmin = 1) o no (esAdmin = 0).

8. Creación de la Tabla Planta
sql

CREATE TABLE Planta (
    Nombre VARCHAR(50) PRIMARY KEY,
    Descripcion VARCHAR(255) NOT NULL
);
Descripción: Crea una tabla llamada Planta con las siguientes columnas:

Nombre: Clave primaria de tipo VARCHAR(50).

Descripcion: Campo obligatorio de tipo VARCHAR(255).

9. Modificación de la Tabla Planta
sql

ALTER TABLE Planta ADD COLUMN NombreCientifico VARCHAR(100);
ALTER TABLE Planta ADD COLUMN Propiedades VARCHAR(255);
ALTER TABLE Planta ADD COLUMN EfectosSecundarios VARCHAR(255);
ALTER TABLE Planta ADD COLUMN Imagen LONGBLOB NOT NULL;
Descripción: Añade las siguientes columnas a la tabla Planta:

NombreCientifico: Campo de tipo VARCHAR(100).

Propiedades: Campo de tipo VARCHAR(255).

EfectosSecundarios: Campo de tipo VARCHAR(255).

Imagen: Campo obligatorio de tipo LONGBLOB.

