
# [[Crear Tablas]]

# [[Crear conexión a la BD]]



## [¿Cómo hacer una base de datos de Usuarios con Roles de acceso? | SQL Server](https://www.youtube.com/watch?v=Xrbl6Xgmi-Q)

## [Como crear tablas y relaciones sin escribir código en sql server](https://www.youtube.com/watch?v=EnFrBZOoa38)

Queda un poco mas claro que en los otros ejemplos, porque solo realiza tareas en SQL Server.

## [Como hacer una Conexión a Base de Datos de SQL Server](https://www.youtube.com/watch?v=1FB_X3adKpQ&list=PL2xycGX1pDXPNeqFPVLajQ4D-KXBd6tQD&index=3)

Desde ASP.NET Visual C# con Web.config
Esplica paso a paso como armar una bd desde SSMS.

## [Bases de datos para sistemas reales](https://www.youtube.com/watch?v=22DVuSmQpNw&list=PLWYKfSbdsjJg3xAytcOjOJuty7VQ4Y5r7)

[ lista de “connection strings”](https://www.connectionstrings.com/sql-server/)

## [SQL Server - Error 15404 Solución - Utilizar diagrama de base de datos](https://www.youtube.com/watch?v=YgfxBywoPHs)

Pocos pasos para poder utilizar diagrama con autenticación de Windows.

## [Creación de BD SQL Server](https://www.youtube.com/watch?v=fxDVA8wXzb8&list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&index=4)

Con pasos interesantes de configuración de SQL Server.  
Creando una tabla desde la opcion de menú Diagramas.  
Y Carpetas de la plantilla MVC.  

## [Cuestiones de claves primarias y claves unicas](https://www.youtube.com/watch?v=QFfZdIZZEpQ&list=PLYAyQauAPx8nUhTpsDF8x3bSDvMWQAsZ5&index=21)

## Backup de una BD con forma de un script

En la BD  
click con el botón alternativo   
Task  
Generate script  
...

Esto genera un backup de la base de datos al estilo mysql.  







## Apunte de comandos para modificar estructura de tablas

~~~ sql
USE DatabaseName

/*Eliminar una tabla*/
DROP table Ciudad
DROP TABLE Alumno

/*Agregar un campo*/
ALTER TABLE Ciudad ADD direccion NVARCHAR(10) NOT NULL

/*Eliminar un campo*/
ALTER TABLE Ciudad DROP COLUMN direccion

/*Renombrar un campo*/
EXEC sp_RENAME 'Ciudad.direccion', 'Direccion', 'COLUMN'

/*Modificar tipo de dato de un campo*/
/*No se puede hacer con comandos identity una vez que la tabla está creada, solo desde SSMS*/
ALTER TABLE Ciudad ALTER COLUMN Nombre nvarchar(30)


go
/*Listar propiedades de una tabla*/
sp_help Ciudad
sp_help Alumno

/*Agregar una clave primaria*/
ALTER TABLE Ciudad ADD PRIMARY KEY (Id) /*De esta forma la clave primaria toma un nombre aleatorio*/
ALTER TABLE Ciudad ADD CONSTRAINT [PK_Ciudad] PRIMARY KEY (Id)

/*Eliminar clave primaria*/
ALTER TABLE Ciudad DROP CONSTRAINT PK__Ciudad__3214EC0797EBCCFB /*El ultimo parámetro es el nombre interno de la clave primaria*/
ALTER TABLE Ciudad DROP CONSTRAINT PK_Ciudad
~~~

## Ejemplo de creacion de tablas relacionadas por comandos SQL

~~~ sql
/**************** Ejemplo de ABM de tablas ****************/
/*Tener en cuenta que IDENTITY trae problemas si no se indica cuando se crea el campo*/
USE a01

CREATE TABLE Ciudad(
	[Id] [int] IDENTITY(1,1),
	[Nombre] [nchar](50) NOT NULL)
go
	 ALTER TABLE Ciudad ADD CONSTRAINT [PK_Ciudad] PRIMARY KEY (Id)
go		


CREATE TABLE [dbo].[Alumno](
	[Id] [int] PRIMARY KEY IDENTITY(1,1),
	[Nombres] [nvarchar](50) NOT NULL,
	[Apellidos] [nvarchar](10) NOT NULL,
	[Edad] [int] NOT NULL,
	[Sexo] [char](1) NOT NULL,
	[FechaRegistro] [datetime] NOT NULL,
	[CodCiudad] [int] NOT NULL)


/*Relaciona las tablas*/
ALTER TABLE [dbo].[Alumno]  WITH CHECK ADD CONSTRAINT [FK_Alumno_Ciudad] FOREIGN KEY([CodCiudad])
REFERENCES [dbo].[Ciudad] ([Id])

ALTER TABLE [dbo].[Alumno] CHECK CONSTRAINT [FK_Alumno_Ciudad]

~~~