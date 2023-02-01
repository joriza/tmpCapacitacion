# [Aprende a programar desde cero con C#, Microsoft .NET y WPF](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/)

## 01 - Introduccion a .NET y Visual Studio

### 006 - SDK de .net

Es un conjunto de bibliotecas y herramientas de desarrollo y ejecución de aplicaciones .net  
Se instala transparentemente con visual studio.  
Pero tambien se puede instalar por separado.  

El SDK contiene:  
- El CLI herramientas de linea de comando para desarrollo
- Driver DotNet es un comando del CLI que ejecuta aplicaciones.
- MSBuild: Es un compilador.
- Runtime: Es solo para ejecutar la aplicación.
- Runtime Library: Librería en tiempo de ejecucion, proporciona tipos de datos primitivos y utilidades fundamentales.
- Runtime ASP.NET Core: Proporciona servicios básicos de aplicaciones conectadas a internet
- Desktop Runtime: Runtime del Escritorio, Consola, Form y WPF.

### 007 - Proyectos

Contiene todos los archivos que se compilan. Fuente, iconos, imagenes, archivos de configuración del proyecto.

#### Extensiones de los proyectos
- .CSPROJ C#
- .VBPROJ Visual Basic
- .DBPROJ Base de Datos

Son documentos XML que el compilador necesita (contenido, requisitos de la plataforma, información de la versión, configuración del servidor web o la base de datos).  

#### **Solución**: Es un contenedor con 1 o más proyectos relacionados (.sln)

### [008 - Creación de Proyectos](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/34821812#overview)

```mermaid
  graph TD;
      A-->B;
      A-->C;
      B-->D;
      C-->D;
```


Todos los proyectos tienen un punto de entrada.
Inician siempre por un método, que desde .NET 6 no se muestra, pero existe.

#### Evitar que muestre partes que desde Net 6 no muestra, y funcionan como si fuera implicitamente.

- Al crear el proyecto, tildar la opción: No usar instrucciones de nivel superior.

Así se vé la plantilla de ejemplo (helloword), sin marcar la opción.
``` C#
// See https://aka.ms/new-console-template for more information
Console.WriteLine("Hello, World!");
```

Y así se vé con la opción marcada.

``` C#
namespace MyFirstApp
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello, World!");
        }
    }
}
```

Todavía falta que muestre los using, y que no los tome de forma implícita.

- Editar archivo de proyecto: (Es un archivo .xml). Sobre el proyecto, clic derecho y seleccionar "Editar archivo de proyecto"
Abre un archivo como este:

``` xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net7.0</TargetFramework>
    <ImplicitUsings>enable</ImplicitUsings>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
``` 

Modificar una línea.

``` xml
    <ImplicitUsings>disable</ImplicitUsings>
``` 

#### Las directivas using

Hacen referencia los espacios de nombres.  
Los espacios de nombres proporcionan un método gerárquico para organizar las bibliotecas y los programas de C#.

**Sintaxis elemental:** Para invocar un método despues del nombre, debe haber paréntesis. Los paréntesis se conocen como el operadó de la invocación del métdo.  
Antes del nombre del método se coloca el nombre de la clase.  
Entre nombre de clase y nombre de método va un punto (.). Al punto se le denomina operador de acceso al miembro.  
La sentencias finaliza con punto y coma (;). Que se denomina operador de final de instrucción.

#### Indicar a VS cual proyecto de la solución debe ejecutar.
![imagen_008-1](img/008-1.png)

#### 009 - Descargar recursos del curso.

#### **Nota:** Abrir rápidamente y desde cualquier carpeta una solución: Haciendo doble clic sobre el archivo .sln  

#### **Nota:** Modo oscuro: Herramientas / Opciones.

### 010 - Modos de compilación y ejecutar desde la consola.

- Debug: Para poder seguir el código.
- Release: Modo más limpio que el tradicional, elimina los archivos temporales de la carpeta bin.

---

## 03 - Introducción a los conceptos básicos

### 017 - [Ejemplo rápido con WinForm y WPF](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/17040996#announcements)

#### **Nota:** Las instancias de tipos de referencia tambien se conocen como objetos

---

## 06 - Algorimos y estructuras de datos

### 036 - [Práctica Matrices](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/18374732#announcements)

Un ejemplo de declaración y uso, pero hay otras formas para hacer lo mismo.

``` C#
namespace MyFirstApp
        static void Main(string[] args)
        {
            //Declaración de arreglos 1
            Console.ForegroundColor = ConsoleColor.Red;
            int[] array1 = new int[3];
            array1[0] = 100;
            array1[1] = 200;
            Console.WriteLine($"array1[0] = {array1[0]} y array1[1] = {array1[1]}");
            Console.ReadKey();
        }
```
Otras formas de declarar matrices

``` C#
namespace MyFirstApp
    int[] array2 = { 1, 3, 5, 7 };

    string[] array3 = { "Lun", "Mar", "Mie", "Jue", "Vie" };

    double[] array4;
    array4 = new double[] { 1.1, 2.2, 3.3, 4.4 };

    int[][] arrayOfArrays = new int[2][];
```


Se pueden recorer con `foreach`.

### 037 - [Práctica Colas y pilas](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/18374734#announcements)

No tiene estructura para ello, pero en el video realiza una implementación de cada uno.

### 038 - [Práctica Listas](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/18374734#announcements)

formas de declarar listas

``` C#
     List<int> list1 = new List<int>();

     List<int> list2 = new List<int>() { 80, 90, 100, 110 };
```

### 039 - [Práctica Otras colecciones](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/18374734#announcements)

``` C#
    //HashSet no acepta objetos repetidos
     HashSet<string> hashSet = new HashSet<string>();
     hashSet.Add("a");

     //SortedSet organiza una lista ascendentemente
    SortedSet<string> sortedSet = new SortedSet<string>();
    sortedSet.Add("d");

    //Disctionary es una lista de llaves/valor
    Dictionary<string, double> fruitCost = new Dictionary<string, double>();
    fruitCost.Add("Mango", 60);
    
    //SortedList es un Dictionary pero ordenado
    SortedList<string, double> fruitCostSorted = new SortedList<string, double>();
    fruitCostSorted.Add("Mango", 60);
```

---

## 07 - Manejo de errores y depuración

Una excepción es cualquier condición de error o comportamiento inesperado que encuentra un programa en su ejecución.

### 041 [Introducción a errores del programa](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/18528120#announcements)

Las exepciones pueden iniciarse debido a:

- Un error en el código propio.
- Recursos del Sistema Operativo no disponibles.
- Condiciones inesperadas en tiempo de ejecución.

En .NET una excepción es un objeto que hereda de la clase `SYSTEM.EXCEPTION`

### 042 [Introducción al manejo estructurado de errores](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/18528124#announcements)

``` C#
     try
     {

     }
     catch
     {

     }
     finally
     {

     }
```

En C# las excepciones las utiliza para lo siguiente:
- Intentar realizar acciones que no pueden completarse correctamente.
- Para controlar errores cuando decide que es razonable hacerlo.
- Para limpiar recursos más adelante.

Las Excepciones las pueden generar:
- El framework de .NET.
- Cualquier biblioteca de terceros.
- El código mismo de la aplicación.

>También se pueden lanzar excepciones dentro del programa con la palabra reservada `THROW`.

En muchos casos una excepción no la produce un método al que el programa ha llamado directamente, sino otro método más abajo en la  pila de llamadas.

### 044 [Práctica Try Catch Finally](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/18528144#announcements)

---

## - 08 Introducción a POO

### 046 [Construcciones básicas del sistema común de tipos en .NET Framework](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20633778#announcements)

CLASS Y STRUCT

Cada una de ellas es básicamente una estructura de datos que encapsula un conjunto de datos y comportamientos que conforman en si, un conjunto . Es decir como una unidad lógica.
Los datos y comportamientos son los miembros de la clase o estructura, e incluyen sus métodos, propiedades y eventos.

#### CLASS:
Una clase es un tipo de referencia. Cuando se se crea un objeto de la clase, la variable a la que se asigna el objeto, contiene solo una referencia a esa memoria. Es solo un apuntador a un espacio en la memoria.   
Cuando la referencia de objeto se asigna a una variable nueva, la nueva variable hace referencia al objeto original. Los cambios originados en una variable se reflejan en la otra variable, porque ambas hacen referencia a los mismos datos.

#### STRUCT

Una estructura es un tipo de valor. Cuando se crea un struct, la variable a la que se asigna el struct, contiene los datos reales de la estructura. Cuando la estructura se asigna a una nueva variable, se copia, y por lo tanto la nueva variable y la variable original continen 2 copias independientes del mismo dato. Los cambios efectuados en una copia no afectan a la otra copia, como sucede en las clases.

En general las clases se utilizan para modelar comportamientos mas complejos o datos que se preveen modificar después de haber creado un objeto de clase
Las estructuras por el contrario, para  modelar comportamientos mas pequeños o datos que no se prevee modificar luego de haber creado la estructura.

### 047 [Clases](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20633888#announcements)

[Link externo:](https://www.youtube.com/watch?v=47bfpYJQyr0)

Al declarar una variable de un tipo de referencia en tiempo de ejecución este contendrá un valor nulo hasta que se cree expresamente una instancia de la clase mediante el operador `new`. O se le asigne un objeto de un tipo compatible que se ha creado en otro lugar. 

``` C#
    class Program
    {
        static void Main(string[] args)
        {
            Customer object1 = new Customer();
            Customer object2 = object1;
        }
    }

    public class Customer
    {

    }
```

Las clases se declaran con la palabra clave `class` seguidas por un identificador único, que por convensión comienza en mayúscula (nombre de la clase). El resto de la definición es el cuerpo de la clase, donde se definen los datos y el comportamiento, campos, propiedades, métodos y los eventos de una clase.  
la palabra `public` indica el nivel de acceso.  
Aunque aveces se usan indistintamente una clase y un objeto son cosas diferentes.  
>Una **clase** define un tipo de objeto, pero no es un objeto en sí.  

>Un **objeto** es una entidad concreta, basada en una clase, que se conoce también como `una instancia de la clase`.

### 048 [Encapsulación](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20634148#announcements)

La encapsulación significa, que un grupo de propiedades, métodos y otros miembros relacionados, se tratan como una sola unidad u objeto.  
Cada clase puede tener distintos miembros de clase entre (propiedades, métodos, eventos.)

[Link externo](https://www.youtube.com/watch?v=fAXJBLfgFVM)

#### Campos y propiedades

**Campos:**

>dsfsfdsf
>
>> asdsfsdfds
>
>dsfsdfsdf

* asdfdasf
- dsfsdf

Me llamo Javier Cristóbal y tengo un blog sobre [productividad mac][blog].
En dicha [web][blog] recopilo artículos sobre todo lo relacionado con automatización, gestión y eficiencia.
[blog]: http://limni.net/blog/


De esta forma podrías insertar una imagen
![nombre de la imagen][img1]  
O dos, sin ensuciar tu espacio de escritura.
![nombre de la imagen2][img2] 
[img1]: /ruta/a/la/imagen.jpg "Título alternativo"
[img2]: /ruta/a/la/imagen2.jpg "Título alternativo"

<http://www.limni.net>

MMD ofrece muchas más posibilidades que MD.
*[MMD]: Abreviación para Multimarkdown
*[MD]: Abreviación para Markdown

```mermaid
  graph TD;
      A-->B;
      A-->C;
      B-->D;
      C-->D;
```

