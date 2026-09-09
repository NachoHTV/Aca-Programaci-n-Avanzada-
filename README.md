# Sistema de Biblioteca

## Descripción

Este proyecto corresponde a un sistema de gestión de biblioteca desarrollado en C# con Windows Forms y SQL Server.

El sistema permite administrar la información de autores, categorías, libros y usuarios, además de registrar préstamos, realizar devoluciones y consultar información de la biblioteca.

El proyecto está organizado por capas para separar las responsabilidades de cada parte del sistema.

---

## Tecnologías utilizadas

- C#
- .NET 8
- Windows Forms
- SQL Server 2025 Express
- SQL Server Management Studio (SSMS)
- Visual Studio 2022
- Microsoft.Data.SqlClient

---

## Estructura del proyecto

La solución está dividida en cuatro proyectos principales:

### Biblioteca.Entidades

Contiene las clases que representan la información utilizada por el sistema.

Entre ellas se encuentran:

- Autor
- Categoría
- Libro
- Usuario
- Préstamo
- Detalle de préstamo

### Biblioteca.Datos

Esta capa se encarga de la comunicación con la base de datos SQL Server.

Contiene las clases encargadas de realizar las operaciones de consulta, inserción, actualización y eliminación de información.

Principales clases:

- Conexion
- AutorDatos
- CategoriaDatos
- LibroDatos
- UsuarioDatos
- PrestamoDatos
- DetallePrestamoDatos
- ConsultasDatos

### Biblioteca.Negocio

Esta capa contiene las reglas de negocio y las validaciones utilizadas por el sistema.

Principales clases:

- AutorNegocio
- CategoriaNegocio
- LibroNegocio
- UsuarioNegocio
- PrestamoNegocio
- ConsultasNegocio

### Biblioteca.Presentacion

Contiene la interfaz gráfica desarrollada con Windows Forms.

Desde esta capa el usuario puede acceder a los diferentes módulos del sistema:

- Autores
- Categorías
- Libros
- Usuarios
- Préstamos
- Devoluciones
- Consultas

---

## Base de datos

La base de datos utilizada por el sistema se llama:

`BibliotecaDB`

La conexión se realiza mediante SQL Server Express utilizando autenticación de Windows.

Servidor utilizado:

`localhost\SQLEXPRESS`

El proyecto incluye el archivo:

`BibliotecaDB.sql`

Este archivo contiene la estructura y los datos necesarios de la base de datos para realizar la instalación del sistema.

---

## Tablas de la base de datos

La base de datos está compuesta por las siguientes tablas:

- Autores
- Categorias
- Libros
- Usuarios
- Prestamos
- DetallePrestamos

Las tablas se encuentran relacionadas mediante claves primarias y claves foráneas para mantener la integridad de la información.

---

## Funcionalidades

### Gestión de autores

Permite:

- Registrar autores.
- Consultar autores.
- Editar autores.
- Eliminar autores.

La información incluye código, nombre, apellidos, nacionalidad y fecha de nacimiento.

### Gestión de categorías

Permite:

- Registrar categorías.
- Consultar categorías.
- Editar categorías.
- Eliminar categorías.

### Gestión de libros

Permite:

- Registrar libros.
- Consultar libros.
- Editar libros.
- Eliminar libros.
- Buscar libros.
- Consultar disponibilidad.

Cada libro se relaciona con un autor y una categoría.

### Gestión de usuarios

Permite:

- Registrar usuarios.
- Consultar usuarios.
- Editar usuarios.
- Eliminar usuarios.

La información incluye documento, nombre, apellidos, teléfono, correo y programa académico.

### Gestión de préstamos

Permite:

- Seleccionar un usuario.
- Seleccionar uno o varios libros.
- Registrar la fecha del préstamo.
- Establecer la fecha esperada de devolución.
- Registrar el préstamo.
- Controlar la disponibilidad de los libros.

Cuando se registra un préstamo, la cantidad disponible del libro se actualiza automáticamente.

### Gestión de devoluciones

Permite:

- Consultar los préstamos registrados.
- Seleccionar el libro que será devuelto.
- Registrar la devolución.
- Actualizar la disponibilidad del libro.

### Consultas

El sistema permite realizar diferentes consultas sobre la información almacenada, entre ellas:

- Libros disponibles.
- Libros prestados.
- Usuarios con préstamos.
- Historial de préstamos.
- Cantidad de libros por categoría.
- Cantidad de libros prestados.

---

## Requisitos para ejecutar el proyecto

Para ejecutar el sistema se requiere:

1. Windows.
2. Visual Studio 2022.
3. .NET 8.
4. SQL Server 2025 Express o una instancia compatible de SQL Server.
5. SQL Server Management Studio.

---

## Instalación de la base de datos

1. Instalar SQL Server y crear una instancia de SQL Server Express.
2. Abrir SQL Server Management Studio.
3. Conectarse al servidor:

`localhost\SQLEXPRESS`

4. Abrir el archivo `BibliotecaDB.sql`.
5. Ejecutar el script para crear la base de datos, sus tablas y los datos iniciales.
6. Verificar que aparezca la base de datos `BibliotecaDB`.

---

## Configuración de la conexión

La conexión se encuentra en el proyecto:

`Biblioteca.Datos`

Archivo:

`Conexion.cs`

La cadena utilizada por el proyecto es:

`Server=localhost\SQLEXPRESS;Database=BibliotecaDB;Trusted_Connection=True;TrustServerCertificate=True;`

Si la instancia de SQL Server tiene un nombre diferente, se debe modificar el nombre del servidor en esta cadena.

---

## Ejecución del sistema

1. Abrir la solución `Biblioteca.sln` en Visual Studio.
2. Establecer `Biblioteca.Presentacion` como proyecto de inicio.
3. Compilar la solución.
4. Ejecutar el proyecto.
5. Desde el menú principal acceder a los diferentes módulos.

---

## Evidencias

El proyecto cuenta con evidencias del funcionamiento de los principales módulos:

- Menú principal.
- Gestión de autores.
- Gestión de categorías.
- Gestión de libros.
- Gestión de usuarios.
- Gestión de préstamos.
- Gestión de devoluciones.
- Módulo de consultas.

Las evidencias muestran la interacción de la aplicación con la base de datos y el funcionamiento de las operaciones principales.

---

## Resultado

El sistema permite gestionar de manera integrada la información básica de una biblioteca, manteniendo separadas las capas de entidades, datos, negocio y presentación.

La aplicación fue probada mediante Visual Studio y SQL Server Express, verificando la conexión con la base de datos y el funcionamiento de los principales módulos.
