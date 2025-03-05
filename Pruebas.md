


# Análisis del Código SQL

## 1. Selección de la Base de Datos
```sql
USE Pvz;
Descripción: Selecciona la base de datos Pvz para realizar operaciones posteriores.

2. Consulta de Todos los Usuarios
sql

SELECT * FROM usuario;
Descripción: Realiza una consulta para obtener todos los registros de la tabla Usuario.

3. Inserción de Usuarios de Prueba
sql

-- Usuario admin
INSERT INTO Usuario (Nombre, Contraseña, Imagen, esAdmin)
VALUES ('User', '123', NULL, False);

INSERT INTO Usuario (Nombre, Contraseña, Imagen, esAdmin)
VALUES ('Kiwi', '123', NULL, TRUE);
Descripción: Inserta dos registros en la tabla Usuario:

Primer registro:

Nombre: 'User'

Contraseña: '123'

Imagen: NULL

esAdmin: FALSE

Segundo registro:

Nombre: 'Kiwi'

Contraseña: '123'

Imagen: NULL

esAdmin: TRUE

4. Comentario sobre Eliminación de Administradores
sql

/*Delete admins
delete from usuario where esAdmin = 1;*/
Descripción: Este es un comentario que sugiere la eliminación de todos los usuarios que son administradores (esAdmin = 1). Sin embargo, está comentado y no se ejecuta.

5. Consulta de Todas las Plantas
sql

SELECT * FROM planta;
Descripción: Realiza una consulta para obtener todos los registros de la tabla Planta.

6. Eliminación de Todas las Plantas
sql

DELETE FROM planta;
Descripción: Elimina todos los registros de la tabla Planta.