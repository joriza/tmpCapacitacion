- [Asp.Net MVC + Entity Framework](#aspnet-mvc--entity-framework)
  - [En Base de Datos y Tablas](#en-base-de-datos-y-tablas)
    - [Método DataBase First](#método-database-first)
      - [Crear la base de datos](#crear-la-base-de-datos)
  - [Crear Usuario SQL SQL Server](#crear-usuario-sql-sql-server)
    - [Inconveniente habitual al crear un usuario](#inconveniente-habitual-al-crear-un-usuario)
    - [Crear Tablas con Diseñador de Base de datoas](#crear-tablas-con-diseñador-de-base-de-datoas)
  - [En Proyecto](#en-proyecto)
  - [Que Contienen las carpetas del proyecto](#que-contienen-las-carpetas-del-proyecto)
  - [Mapear el modelo de datos](#mapear-el-modelo-de-datos)
  - [Agregar una opción al menú](#agregar-una-opción-al-menú)
  - [Crear controlador](#crear-controlador)
  - [Crear Vista](#crear-vista)
    - [Cargar datos en el controlador para enviar a la vista](#cargar-datos-en-el-controlador-para-enviar-a-la-vista)
    - [Condicional if en razor](#condicional-if-en-razor)
  - [Agregar método para registrar nuevo registro - HttpGet](#agregar-método-para-registrar-nuevo-registro---httpget)
  - [Modificar estuctura física de la BD y reflejar en proyecto](#modificar-estuctura-física-de-la-bd-y-reflejar-en-proyecto)
    - [Método 1 - Actualizar modelo](#método-1---actualizar-modelo)
    - [Método 2 - Eliminar tablas](#método-2---eliminar-tablas)
    - [Ambos métodos](#ambos-métodos)
    - [Agregar método para registrar nuevo registro - HttpPost](#agregar-método-para-registrar-nuevo-registro---httppost)
    - [Evitar perder los DataAnnotation al actualizar modelo con EF](#evitar-perder-los-dataannotation-al-actualizar-modelo-con-ef)

<div class="page"/>

# [Asp.Net MVC + Entity Framework](https://www.youtube.com/watch?v=fxDVA8wXzb8&list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&index=4)

Capítulos: 12 Los mas interesantes son del 3 al 9.  
Tiene muchos tips interesantes y prácticos.
Controladores creados manualmente.  
Vistas con Scaffolding, pero solo para tener una base con la cual comenzar a trabajar.  

ProyectoNombre: CRUD-Alumnos  
ProyectoTipo: Net Framework  
MarcoVersion: 4.5.2  
MVC  
BD: SQL Server DbFirst con update de bd con EF.  
CntTablas: 2  
EF / ADO: EF  
LQ:  Si  
 
<div class="page"/>

## En Base de Datos y Tablas

> [[_SQL Server| Más apuntes de SQL Server]]

### Método DataBase First

#### [Crear la base de datos](https://youtu.be/fxDVA8wXzb8?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=438)

Desde Diagrams del Enterprise Management

## [Crear Usuario SQL SQL Server](https://youtu.be/fxDVA8wXzb8?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=519)


### [Inconveniente habitual al crear un usuario](https://youtu.be/fxDVA8wXzb8?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=663)

La primera vez que se crea un usuario y el servidor solo está habilitado Autenticación de Windows.    

> Otro posible inconveniente:  
![[_SQL Server#SQL Server - Error 15404 Solución - Diagrama base de datos]]

### [Crear Tablas con Diseñador de Base de datoas](https://youtu.be/fxDVA8wXzb8?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=872)

 de Enterprise Management

Script para crear la tabla de forma sencilla, y que nos quede igual que la utializada en el ejemplo
~~~ sql
CREATE TABLE [dbo].[Alumno](
	[id] [int] IDENTITY(1,1) NOT NULL,
	[Nombres] [nvarchar](50) NOT NULL,
	[Apellidos] [nvarchar](10) NOT NULL,
	[Edad] [int] NOT NULL,
	[Sexo] [char](1) NOT NULL,
	[FechaRegistro] [datetime] NOT NULL,
 CONSTRAINT [PK_Alumno] PRIMARY KEY CLUSTERED 
(
	[id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
~~~

<div class="page"/>

---
---

## En Proyecto

## [Que Contienen las carpetas del proyecto](https://youtu.be/fxDVA8wXzb8?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=1092)

El uso habitual de cada carpeta

## [Mapear el modelo de datos](https://youtu.be/vhQ92Is7X4Q?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=16)

En la carpeta Model.  
Nuevo elemento.  
Tipo Datos.  
ADO.NET Entity Data Model  
Colocar nombre al modelo.  
EF Designer desde base de dato.  
> A mi me lanza un error.  
Eliminar el contenido de la carpeta Model.  
Eliminar en archivo Web.config La etiqueta y el contenido de <connectionStrings>

Una vez que muestra el diagrama de bd, botón guardar.


## [Agregar una opción al menú](https://youtu.be/vhQ92Is7X4Q?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=635)

Si utilizamos el menú que trae la plantilla.  
Editar el archivo  
Views\Shared\_Layout.cshtml  
Agregar una línea como la siguiente:  
Donde los parámetos son:  
- Texto a mostrar en el menú  
- Nombre del método
- Nombre del controlador al que pertenece el método

~~~c#
<li>@Html.ActionLink("LabelMenu", "MethodName", "ControllerName")</li>
~~~

## [Crear controlador](https://youtu.be/vhQ92Is7X4Q?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=704)

Agregar  
Controlador  
Controlador MV5 en Blanco  

## [Crear Vista](https://youtu.be/vhQ92Is7X4Q?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=948)

Click derecho en el nombre del método.  
Elegir el tipo de plantilla (Listar, crear ...)  
Seleccionar el Modelo en el que se va a basar la plantilla.  
Aparentemente no es obligatorio indicar el context.  

### [Cargar datos en el controlador para enviar a la vista](https://youtu.be/vhQ92Is7X4Q?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=1064)

Lo que envía en este ejemplo es una lista.  
Utiliza LinQ como opcion para realizar una query que no entregue la totalidad de los datos.

### [Condicional if en razor](https://youtu.be/vhQ92Is7X4Q?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=1541)

Este ejemplo se aplica sobre una vista.  

## [Agregar método para registrar nuevo registro - HttpGet](https://youtu.be/vhQ92Is7X4Q?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=1689)

Por omisión, el método es HttpGet, que carga la vista para recopilar datos por parte del usuario.
El método Create se agrega en el controlador de la entidad Alumno.
De la vista generada con scaffolding, se elimina el campo de fecha, porque se generará por código.

## [Modificar estuctura física de la BD y reflejar en proyecto](https://youtu.be/vhQ92Is7X4Q?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=1976)

### Método 1 - Actualizar modelo

En VS, en la carpeta Models, en el archivo .edmx, boton derecho, actualizar Modelo.  
Indicar las tablas que debe actualizar, pero suele fallar este proceso.

### Método 2 - Eliminar tablas 

Ir a lo seguro, eliminar las tablas.  
Guardar.   
Click con botón derecho, actualizar modelo desde base de datos.  
Indicar las tablas con las que se debe proceder.   

### Ambos métodos

En los archivos .tt de la carpeta Models.  
Click con botón derecho, ejecutar herramienta personalizada.  

### [Agregar método para registrar nuevo registro - HttpPost](https://youtu.be/Xn_G44-h8es?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=21)

Antes de intentar guardar los datos que vienen de la vista, el método guardar verifica según lo que esté definido en el modelo, que se cumpla esas indicaciones con [DataAnnotation](https://learn.microsoft.com/es-es/aspnet/core/mvc/models/validation?view=aspnetcore-7.0).

> Tener en cuenta que se borrarán los DataAnnotation que se escriban en un modelo con dbFirst si se regenera el modelo.

### [Evitar perder los DataAnnotation al actualizar modelo con EF](https://youtu.be/Xn_G44-h8es?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=368)

Crea una clase que contiene una copia de la estructura del modelo de la tabla física.

En Models crear una clase, que se llama AlumnoCE.  
Que va a ser como una clase parcial, que va a funcionar como un complemento de Alumno.cs.  

