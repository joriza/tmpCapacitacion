# dvNet

## Del curso de Desarrollo Web con Blazor y .Net Core 3 de Platzi

la palabra reservada using es como los import en python, solo que en VS suele proponer el using y el nugget está instalado.

EntityFrameworkCore
Así se debe llamar el nugget que se debe instalar, ojo hay uno parecido en cantidad de descargas que termina con .Relacional

Ctrl+KD para que formatee el código (Similar Black en Python)

Proyecto Librería de clases para la definción del modelo


Otro Proyecto Librería de clases la capa de acceso a datos, en el caso de la solucion Inventory se utiliza EntotyFramework
Se debe agregar referencia a la capa Entities

Para poder crear la conexion a la base de datos se debe instalar el paquete nugget EntityFrameworkCore.SqlServer.
Los paquetes instalados se ven en el explorador de soluciones / solucion / proyecto / Dependencias / Paquetes

Para poder migrar la imprementacion de la capa de datos con EF es necesario instalar el nugget EntityFrameworkCore.Tools

Si falla, puede ser porque se necesite marcar el proyecto que corresponde a la capa de acceso a datos como proyecto de inicio de la solución.

Para poder ejecutar la migración, se debe ejecutar el comando
add-migration en la "Consola de Administración de paquetes"
Crea un archivo .cs con todos los comandos para la base de datos.

En Inventory no se usa, pero para obtener la cadena de conexion.
En VS ir a: Ver / Explorador de objetos de SQL Server
Si no apare el motor, hacer click en agregar para agregarlo. Y sobre la BD clic derecho propiedades buscar la cadena de conexion o connection string.
// Data Source=HCI-NOTE227\SQLEXPRESS;Initial Catalog=BlazorCRUD;Integrated Security=True;Connect Timeout=30;Encrypt=False;TrustServerCertificate=False;ApplicationIntent=ReadWrite;MultiSubnetFailover=False

-Para que genere el script para la estructura segun InventaryContext
add-migration <FirsMigration>
-Para aplicar el script de estructura
update-database

-Para poblar la base de datos segun Segun InventaryContext
add-migration <AddData>
-Para aplicar el script de estructura
update-database


## ! Ver que es una clase static en c# (Como public static void)


Comp y pag para bodegas, categorias, almac, io

--------------------------------------------------------------------------------------------

## [Pasar datos de los Controladores a las Vistas](https://www.youtube.com/watch?v=M3svi5v72XE&list=PL8neH3UPvUd4i9r9NHhhuGvtg8sxNDD-m&index=7)

La vista se limia a mostrar los datos que le envía el controlador.
O tomar datos nuevos y enviárselos al controlador.

### ViewData

Es un diccionario.
Es una desventaja, porque necesitamos escribir exactamente el nombre de la clave, y por estan dendro de una cadena, no hay ayuda del intellisence. Y en tiempo de ejecución simplemente la no mostrará nada.

~~~ c#
        public ActionResult Index()
        {
            ViewData["DNI"] = "12345678";
            ViewData["Nombres"] = "Jorge Javier";
            ViewData["Apellidos"] = "Izaguirre";

            return View();
        }
~~~

~~~ html
<hr />

Mi nombre es <b>@ViewData["Nombres"]</b> y mi apellido es <b>@ViewData["Apellidos"]</b> <br />
y mi DNI es <b>@ViewData["DNI"]</b>
~~~


### ViewBag
Es similar a ViewData, pero aprovecha las capacidades de la programación dinámica que ofrece C# desde la versión 4.0 para, en lugar de usar cadenas, usar las propiedades.


~~~ c#
        public ActionResult Index()
        {
            ViewBag.DNI = "12345678";
            ViewBag.Nombres = "Jorge Javier";
            ViewBag.Apellidos = "Izaguirre";

            return View();
        }
~~~

~~~ html
<h2>Usando ViewBag</h2>
Mi nombre es <b>@ViewBag.Nombres</b> y mi apellido es <b>@ViewBag.Apellidos</b>
<br />
y mi DNI es <b>@ViewBag.DNI</b>
~~~

### ViewModel

Lo hace usando la propiedad model. Lo que se pasa es un objeto.
A diferencia de los métodos anteriores, el controlador no tiene una propiedad model. En su lugar se utiliza una sobrecarga del método View y se envía el objeto como parámetro.

En la carpeta Models, crear una clase, en este caso se llama PersonaModel
~~~ c#
namespace MvcTest.Models
{
    public class PersonaModel
    {
        public int DNI { get; set; }
        public string Nombres { get; set; }
        public string Apellidos { get; set; }
    }
}
~~~

En el controlador:
~~~ c#
    public ActionResult Index()
    {
        PersonaModel p = new PersonaModel
        {
            DNI = 21735582,
            Nombres = "Jorge Javier",
            Apellidos = "Izaguirre"
        };

        return View(p);
    }
~~~

En la Vista:
~~~ html
@model MvcTest.Models.PersonaModel
<h2>Usando ViewModel</h2>
Mi nombre es <b>@Model.Nombres</b> y mi apellido es <b>@Model.Apellidos</b>
<br />
y mi DNI es <b>@Model.DNI</b>

~~~



> [!NOTE]
> Una forma de escribir una nota.

