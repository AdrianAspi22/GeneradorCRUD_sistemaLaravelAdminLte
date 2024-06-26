# Documentación básica del generador de CRUD a partir de un DDL

El programa Procesador de DDL es una herramienta que analiza un script DDL (Data Definition Language) utilizado para crear tablas en una base de datos SQL. El usuario puede ingresar el script DDL en un área de texto y luego procesarlo haciendo clic en un botón. El programa extrae información importante de la definición de la tabla, como nombres de variables, tipos de datos, tamaños de datos y claves primarias.

## Funcionalidades principales:

1. **Análisis de DDL:** El programa procesa el script DDL ingresado por el usuario y extrae información relevante sobre la estructura de la tabla que se está creando.

2. **Visualización de variables:** Después de procesar el DDL, el programa muestra una nueva ventana que contiene una lista de variables extraídas de la definición de la tabla. Cada variable se muestra junto con su tipo de dato y tamaño (si corresponde). También se proporciona la opción para marcar una variable como clave primaria.

3. **Guardar cambios:** Una vez que el usuario ha revisado y posiblemente modificado las variables en la nueva ventana, puede guardar los cambios. Al hacerlo, se abre un buscador de archivos para que el usuario seleccione la carpeta del proyecto Laravel donde se generarán los archivos necesarios.

4. **Generación de archivos CRUD:** Después de seleccionar la carpeta del proyecto Laravel, el programa genera automáticamente todos los archivos necesarios para implementar un CRUD (Create, Read, Update, Delete) para la tabla definida en el script DDL. Esto incluye la creación de archivos de vista (Blade), controlador (Controller), modelo (Model) y migración (Migration), así como la adición de la ruta correspondiente en el archivo de rutas del proyecto.

## Uso del programa:

1. **Ingreso del script DDL:** El usuario debe copiar y pegar el script DDL que define la tabla en el área de texto proporcionada.
A continuación se muestra un ejemplo de cómo debería ser un script DDL que define la creación de una tabla en SQL:
```sql
CREATE TABLE PRODUCTOS
(
  NOREG Integer NOT NULL,
  FECHA Date,
  DETALLE Varchar(128),
  UNIDAD Varchar(18),
  PRODUCTO Varchar(18),
  CALCULO Smallint,
  CANCELADO Integer,
  RESTO Smallint,
  TURNO Smallint,
  TIPO_SESION Smallint,
  NICK Varchar(32),
  CODIGO_VENDEDOR Varchar(36),
  RESPONSABLE Varchar(128),
  LINK Varchar(32),
  ULINK Varchar(32),
  DUAL Integer,
  FECHADETALLE Varchar(75),
  CANTIDAD Numeric(16,6),
  PC Numeric(16,6),
  PV Numeric(16,6),
  MONTO Numeric(16,6),
  UNIDADPRODUCTO Varchar(52),
  PU Numeric(16,6),
  LIBROCONTABLE Varchar(4),
  CUENTACONTABLE Varchar(12),
  ESPRODUCTO Smallint DEFAULT 1,
  MARCA Varchar(128),
  TAMANIO Varchar(16),
  PCUSD Numeric(9,6),
  DESPLIEGUE Smallint DEFAULT 0,
  TIPOISC Smallint,
  TASAISC Numeric(12,6),
  TIPODSCTO Smallint,
  DSCTOUNIT Numeric(12,6),
  TIPOCARGO Smallint,
  CARGOUNIT Numeric(12,6),
  TIPOOPERACION Smallint,
  PR Numeric(12,6),
  MINCOMPRA Numeric(12,6),
  FECHAVENCIMIENTO Date,
  VERSION_IMG Smallint,
  SERIE Varchar(5),
  CODIGOSUNAT Varchar(10),
  AFECTOICBPER Smallint,
  UBICACION Varchar(64),
  PESO Numeric(12,2),
  PMAYOR Numeric(12,4),
  STOCKMINIMO Numeric(12,4),
  ESTADOSERVPROD Smallint DEFAULT 0,
  FACTURABLE Smallint DEFAULT 0,
  PERECIBLE Smallint DEFAULT 0,
  CLASIFICADOR Varchar(2),
  NROLOTE Varchar(32),
  PRESENTACION Varchar(64),
  RECETA Smallint DEFAULT 0,
  PRIMARY KEY (NOREG)
);
```
Este es el ejemplo que se uso para probar nuestro programa, no olvidar la primary key al final, siempre va hacer necesario.

2. **Procesamiento del DDL:** Después de ingresar el script DDL, el usuario debe hacer clic en el botón "Procesar" para iniciar el análisis del script y la extracción de información.

3. **Revisión y modificación:** Una vez procesado el DDL, se muestra una nueva ventana con la lista de variables extraídas. El usuario puede revisar esta información y realizar modificaciones si es necesario.

nota: la ventana que salga puede ser pequeña, lo recomendable es agrandarla horizontalmente para poder ver todas las opciones para modificar. 

4. **Guardar cambios:** Después de revisar y posiblemente modificar las variables, el usuario puede hacer clic en el botón "Guardar cambios" para guardar los cambios y continuar con la generación de los archivos CRUD en la carpeta del proyecto Laravel.

nota: al momento de precionar el boton se abira un buscador de archivos, debes selecionar la carpeta de tu proyecto laravel.

5. **Implementación del CRUD:** Después de guardar los cambios, el programa generará automáticamente los archivos necesarios para implementar un CRUD completo para la tabla definida en el script DDL. Estos archivos se crearán en la carpeta del proyecto Laravel seleccionada por el usuario.

nota: para poder ver los cambios faltaria agregar las rutas correspondientes al dashboard

## Requisitos del sistema:

- Python 3.x instalado en el sistema.
- Tkinter (biblioteca estándar de Python para interfaces gráficas) debe estar disponible en el entorno de Python.
- El programa está diseñado para ser utilizado en un entorno de desarrollo Laravel, por lo que se espera que el usuario tenga conocimientos básicos de desarrollo web con Laravel y una estructura de proyecto Laravel establecida.

Con el programa Procesador de DDL, los usuarios pueden agilizar el proceso de desarrollo al automatizar la creación de archivos y la configuración necesaria para implementar operaciones CRUD en una tabla de base de datos definida en un script DDL.
