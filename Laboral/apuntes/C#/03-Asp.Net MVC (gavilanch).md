- [Asp.Net MVC + Entity Framework](#aspnet-mvc--entity-framework)
  - [Controladores y acciones | Controladores](#controladores-y-acciones--controladores)
    - [Routing y RouteConfig | Controladores](#routing-y-routeconfig--controladores)
    - [ActionResult mvc | Controladores](#actionresult-mvc--controladores)
  - [ContentResult en MVC | Controladores](#contentresult-en-mvc--controladores)
  - [JSON y JSONResult MVC 5 | Controladores](#json-y-jsonresult-mvc-5--controladores)
    - [Devolver un json](#devolver-un-json)

<div class="page"/>

# [Asp.Net MVC + Entity Framework](https://www.youtube.com/watch?v=YzC-FYg66xA&list=PL0kIvpOlieSNWR3YPSjh9P2p43SFnNBlB&index=1)
Capítulos: 116 Muy didáctico
Tiene muchos tips interesantes y prácticos.

ProyectoNombre:   
ProyectoTipo: Net Framework  
MarcoVersion:  
MVC  
BD: 
CntTablas: 
EF / ADO: 
LQ:  
 
<div class="page"/>

## [Controladores y acciones | Controladores](https://www.youtube.com/watch?v=Euw2EDgqzIg)

Como es la relacón entre controladores y vistas.

### [Routing y RouteConfig | Controladores](https://www.youtube.com/watch?v=P6ZnsOjFuLk)

Como son las reglas de ruteo.

>action = método

### [ActionResult mvc | Controladores](https://www.youtube.com/watch?v=tA__zrBqdcU)

ActionResult es general, aunque por lo general se usa para devolver una vista.  
Pero tambien existen otros Result, como:  
ViewResult
File Result

## [ContentResult en MVC | Controladores](https://www.youtube.com/watch?v=MnA6It421ec)

Como devolver un string desde un action.
Se ultiliza el método content.
Permite definir el content type, para indicar el tipo de lo que se vá a devolver.

~~~ C#
public ContentResult Index()
{
    return Content("Texto libre");
}
~~~

## [JSON y JSONResult MVC 5 | Controladores](https://www.youtube.com/watch?v=IhmEFS1Gzds)

### Devolver un json

Como el ejemplo es un GetRequest y no un Post.
Se debe indicar explicitamente que se vá a permitir:
`JsonRequestBehavior.AllowGet`

~~~ C#
namespace Temp03_Varios.Controllers
{
    public class Persona
    {
        public string Nombre { get; set; }
        public int Edad { get; set; }
    }

    public class HomeController : Controller
    {
        public ActionResult Index()
        {
            var persona1 = new Persona() { Nombre = "Jorge", Edad = 99 };
            return Json(persona1, JsonRequestBehavior.AllowGet);
        }
    }
}
~~~

