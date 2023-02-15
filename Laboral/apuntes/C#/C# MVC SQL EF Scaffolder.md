# [CRUD c# sql server MVC, desde CERO](https://www.youtube.com/watch?v=0Gu56u71G18)

CRUD para una tabla 
Con sql server
EntityFramework con Scaffolder


Crear proyecto C##  / Web / Aplicacion web ASP.NET (.NET Framework)

Framework: NET Framework 4.61.1

Plantilla: MVC

[Partes de una aplicación MVC](https://youtu.be/0Gu56u71G18?t=150)

Cada uno de los controladores (.cs) tiene al menos ActionResult con un nombre de método que es igual que un archivo .cshtml en la vista (carpeta Views).

![fig01](.\img\mvc01.png)

Todo lo que tiene el controlador, son operaciones, elementos, interacciones con las vistas.

[Layout y Estructura](https://youtu.be/0Gu56u71G18?t=395)

[Revisando las vistas del proyecto](https://youtu.be/0Gu56u71G18?t=645)

En HomeControler asigna texto a variables y la vista lo puede imprimir con una llamada Razor.

[Creando una vista](https://youtu.be/0Gu56u71G18?t=794)

Para agregar manualmente una vista sencilla:
En agregar vista, solo se debe ingresar el nombre del archivo que corresponderá a la vista. Y seleccionar la página del Layout (Carpeta Shared).  
El archivo creado tiene una referencia a la página del layout.  
Cada vista debe estar enlazada con un controlador, sino la vista existirá, pero no se podrá acceder a la vista.

[Enlazar una vista al menú](https://youtu.be/0Gu56u71G18?t=1035)

En el archivo del layout agregar:
    
    <li>@Html.ActionLink("Misión", "Mision", "Home")</li>

Donde los parámetros son: Texto en el menú, Método (y vista) al que llama, Controlador al que pertenece

[Preparando Bd](https://youtu.be/0Gu56u71G18?t=1134)

En el campo que es clave primaria, activar la propiedad Identity, para que el campo sea auto incremental.

[Instalando Entity Framework](https://youtu.be/0Gu56u71G18?t=1330)

En el proyecto: Click alternativo.
Administrar paquetes nuggets.

[Conexion a Bd y Generar modelos](https://youtu.be/0Gu56u71G18?t=1455)

Agregar nuevo elemento / Datos / ADO.NET Entity Data Model

[Generar Controles y Vistas Usando EF](https://youtu.be/0Gu56u71G18?t=1697)

Se necesita crear las vistas y los controladores de esas vistas.  
Como EF trabaja con la información que tienen los modelos y se puede generar en forma automática.  
En la Carpeta Controllers Agregar controlador: MVC con vistas que usa EF. (Que genera las vistas y el controlador a partir del modelo definido).  
Seleccionar Modelo, contexto de datos y solo selecciona el Layout por defecto.
Escribir el nombre que se le vá a dar al controlador.  
Si Visual Studio muestra error al confirmar este paso, es necesario compilar el proyecto nuevamente y repetir la operación para crear el controlador.  

[Revisando el Crud](https://youtu.be/0Gu56u71G18?t=1903)

Agrear la opcion del menú en el Layout con la directiva razor: `@Html.ActionLink`  

Eso es todo cuando se hace con EF. Crea el archivo con los controladores y con las Vistas.


![[Visual Studio]]

