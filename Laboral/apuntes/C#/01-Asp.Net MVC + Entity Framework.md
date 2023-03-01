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
  - [Agregar método para registrar nuevo registro](#agregar-método-para-registrar-nuevo-registro)
  - [Modificar estuctura de BD y reflejar en proyecto](#modificar-estuctura-de-bd-y-reflejar-en-proyecto)

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

## [Agregar método para registrar nuevo registro](https://youtu.be/vhQ92Is7X4Q?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=1689)

El método Create se agrega en el controlador de la entidad Alumno.
De la vista generada con scaffolding, se elimina el campo de fecha, porque se generará por código.

## [Modificar estuctura de BD y reflejar en proyecto](https://youtu.be/vhQ92Is7X4Q?list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&t=1976)

Modificar la estructura física de la BD.

En VS en el modelo, boton derecho y actualizar cambios.