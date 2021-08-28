
# SQLite Cheat Sheet</h1>

## Crear Tabla

```
CREATE TABLE nombre_tabla (
nombre_columna tipo de dato y/o restrictor,
nombre_columna tipo de dato y/o restrictor
)
```
>Esto Crea una nueva tabla. Para ver los tipos de restrictores buscalos a continuacion.


## Insertar datos

```
INSERT INTO nombre_tabla (nombre_columna2, nombre_columna4)
VALUES
(dato1, dato2),
(dato3, dato4);
```
>No es necesario llenar todas las columnas de la tabla. A menudo es útil omitir columnas con claves primarias o inserción de valores predeterminados.

## Modificar Tablas
```
UPDATE nombre_tabla
SET nombre_columna5 = valor5
WHERE expresion
```
>Esto actualizará la columna dada con el valor dado en donde la expresión se evalúe como verdadera (generalmente clave primaria específica).

## Alterar Tablas

La función ALTERAR TABLE está limitada en SQLite.
>You can either rename the table with:
```
ALTER TABLE nombre_tabla RENAME TO nuevo_nombre_tabla
```
>O agregue una nueva columna con:
```
ALTER TABLE nombre_tabla ADD COLUMN definicion_columna
```
>No es posible cambiar las definiciones de columna de tablas existentes.

## Borrar Tabla
```
DROP TABLE nombre_tabla
```

## Seleccionar desde Tabla 
```
SELECT tabla1.columna1, tabla.2columna2,
FROM tabla1, tabla2
WHERE expresion
ORDER BY tabla1.columna1 order
```
>ORDER BY es opcional, las posibles formas de ordenar son ASC (ascendente) y DESC (descendente).

## Tipo de Datos

- NULL valor nulo
- INTEGER valor Entero
- REAL flotante
- TEXT Texto con codificacion UTF
- BLOB Blob-Data (almacenado como entrada)
- BOOLEAN Se almacenará como entero (0 para falso, 1 para verdadero)


## Restrictores

- PRIMARY KEY Establece la columna como clave principal. Las restricciones NOT NULL y UNIQUE se establecerán automáticamente.
- NOT NULL Evita que la columna tenga valores vacíos (null).
- UNIQUE Cada valor de la columna debe ser único.
- INTEGER PRIMARY KEYs Se convierte automático en ROWID y se incrementará solo. Se puede acceder a esta columna como ROWID, OID, _ROWID_ o el nombre de la columna.
