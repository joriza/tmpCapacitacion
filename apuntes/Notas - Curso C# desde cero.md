# [Aprende a programar desde cero con C#, Microsoft .NET y WPF](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/)

# $\Bbb{.NET}$

# $\colorbox{blue}{.NET}$

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
---

## - 08 Introducción a POO

### 046 [Construcciones básicas del sistema común de tipos en .NET Framework](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20633778#announcements)

CLASS Y STRUCT

Cada una de ellas es básicamente una estructura de datos que encapsula un conjunto de datos y comportamientos que conforman en si, un conjunto . Es decir como una unidad lógica.
Los datos y comportamientos son los miembros de la clase o estructura, e incluyen sus métodos, propiedades y eventos.

#### CLASS:
Una clase es un tipo de referencia. Cuando se se crea un objeto de la clase, la variable a la que se asigna el objeto, contiene solo una referencia a esa memoria. Es solo un apuntador a un espacio en la memoria.   
Cuando la referencia de objeto se asigna a una variable nueva, la nueva variable hace referencia al objeto original. Los cambios originados en una variable se reflejan en la otra variable, porque ambas hacen referencia a los mismos datos.

[**valor vs referencia*](https://www.youtube.com/watch?v=R_8iA6DjGmA)

#### STRUCT

Una estructura es un tipo de valor. Cuando se crea un struct, la variable a la que se asigna el struct, contiene los datos reales de la estructura. Cuando la estructura se asigna a una nueva variable, se copia, y por lo tanto la nueva variable y la variable original continen 2 copias independientes del mismo dato. Los cambios efectuados en una copia no afectan a la otra copia, como sucede en las clases.

En general las clases se utilizan para modelar comportamientos mas complejos o datos que se preveen modificar después de haber creado un objeto de clase
Las estructuras por el contrario, para  modelar comportamientos mas pequeños o datos que no se prevee modificar luego de haber creado la estructura.

---

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

---

### 048 [Encapsulación](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20634148#announcements)

La encapsulación significa, que un grupo de propiedades, métodos y otros miembros relacionados, se tratan como una sola unidad u objeto.  
Cada clase puede tener distintos miembros de clase entre (propiedades, métodos, eventos.)

[Link externo](https://www.youtube.com/watch?v=fAXJBLfgFVM)

#### Campos y propiedades

Representan información que contiene un objeto

#### **Campos:** 

Se parecen a las variables, ya que se pueden leer o establecer directamente, y son sujetos a los modificadores de acceso. Solo es accesible desde la propia clase.

#### **Propiedades:** 

Tienen descriptores de acceso get y set, que establecen mas control sobre la forma en que se establecen o devuelven los valores.  

``` C#
    public string SecondName 
    { 
        get
        {
            return _secondName;
        } 
        set
        {
            _secondName = value;
        } 
    }
```

Las propiedades implementadas automáticamente no pueden ser de solo lectura.

``` C#
    public string FirstName { get; set; }
```

#### **Método:** 

Es una acción que un objeto puede realizar. Consta de un modificador de acceso, tipo, nombre y posibles parámetros. Se declara dentro de una definición de clase.

``` C#
    public int sampleMethod(string sampleParam)
    {
        return 0;
    }
```

Una clase puede tener varias implementaciones o sobrecargas del mismo método. Se diferencian por el número o tipo de parámetros

``` C#
    public int sampleMethod(int sampleParam)
    {
        return 0;
    }
```

#### [**Constructores:**](https://www.youtube.com/watch?v=t0c1H2Juj-M&t=3s) 

Son métodos de clase que se ejecutan automáticamente cuando se crea un objeto de un tipo determinado. Normalmente los constructores inicializan los miembros de los datos del nuevo objeto. Solo puede ejecutarse una vez cuando se crea la clase. Se ejecuta antes que cualquier otro código en una clase.  
Se pueden crear sobrecargas del constructor, de la misma forma que para cualquier otro método.
No tiene un tipo y se llama igual que la clase.

``` C#
    public sampleClass()
    {
        FirstName = "Sin Nombre"
    }
    public sampleClass(string firstName, string secondName)
    {
        FirstName = firstName;
        _secondName = secondName;
    }
```

#### **Finalizadores:**

Se utilizan para destruir instancias de clase. Solo puede haber un finalizador para una clase.

``` C#
    ~sampleClass()
    {
        ...
    }
```

#### **Eventos:** 

Cuando ocurre algo relevante, los eventos habilitan una clase u objeto para notificarlo a otras cases u objetos.
La clase que envía o genera el evento, recibe el nobre de publicador.
Las clases que reciben, o controlan el evento, se denominan suscriptores.
Para declarar un evento se utiliza la palabra `event`.

#### **Clases anidadas:** 

Se denomina así, cuando una clase es definida dentro de otra clase.
De forma predeterminadad, una clase anidada es privada.

#### [**Modificadores de acceso:** ](https://www.youtube.com/watch?v=fAXJBLfgFVM)

Todas las clases y miembros de clase, pueden especificar el nivel de acceso que proporcionan a otras clases mediante los modificadores de acceso.

- **Public**: Permite obtener acceso al tipo miembro a cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a este.
- **Protected**: De la misma clase, o una clase derivada.
- **Private**: Solo permite acceso al tipo miembro de la misma clase.
- Internal: A cualquier miembro del mismo ensamblado, pero no de otro ensamblado. (.exe o .dll - En la solución, es otro proyecto)
- Protected Internal: Una combinación de ambas simultaneamente.
- Private Protected: Una combinación de ambas simultaneamente.

---

### 049 [Herencia](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20634184#announcements)

No todos los miembros de una clase base, los heredan las clases derivadas.  
Los constructores y los finalizadores no se heredan.  
Cada calse debe tener sus propios constructores y finalizadores.  
Se heredan los demas miembros de una clase base. Que dichos miembros estén o no visibles, depende de su accesibilidad.

#### **Override:** 

Las clases derivadas pueden invalidar los métodos derivados al proporcionar una implementación alternativa.  
Para poder invalidar un miembro, el miembro de la clase base debe marcarse con la palabra clave virtual, que de forma predeterminada no están marcados como virtual.
La herencia solo se aplica a clases e interfaces.
Otros tipos de estructura como: STRUCT, DELEGATES o ENUM, no soportan la herencia.

``` C#
    public class A
    {
        public virtual void VirtualMethod()
        {
            // Código del método
        }
        public void NotVirtualMethod()
        {
            // Código del método
        }
    }
    public class B : A
    {
        public override void VirtualMethod()
        {
            // Código del método
        }
        public override void NotVirtualMethod() // Este caso marca error de compilador.
        {
            // Código del método
        }
    }
```

#### [**Clases Abstractas:**](https://www.youtube.com/watch?v=iRELmavR_eY&t=390s)

En algunos casos una clase derivada debe invalidar la implementación de la clase base.
Los miembros de la clase base marcados con la palabra clave abstract, requieren que las clases derivadas los invaliden, forzosamente.
Estas no permiten crear instancias de ellas. No se puede crear una instancia de una clase abstracta.
Una clase abstract sin ningún método abstract, indica que representa un concepto abstracto, que se comparte entre varias clases concretas.
La palabra reservada abstract, se utiliza para forzar que la clase derivada proporcione una implemtación.

#### **Herencia implícita:** 

Además de los tipos que pueden heredar mediante herencia única, todos los tipos heredan implicitamente de Object, o de un tipo derivado de este.

---

### 050 [Enumeraciones](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/29991256#announcements)

Es un tipo de valor definido por constantes. El índice comienza desde 0. Como es un tipo por valor, no es necesario crear una instancia. 
Suelen ayudar bastante a interpretar el código para quien lo lee.

``` C#
    piblic enum Days
    {
        Lunes,
        Martes.
        Miercoles
    }
        // Para invocarlo
        Days day = Days.Friday;
```

[Link:](https://www.youtube.com/watch?v=bnkphc-DjGA)

---

### 051 [Práctica clases, encapsulación y herencia](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20634242#announcements)

**Clase sealed**: (sellada) Esta palabra se utiliza para indicar que la clase no puede servir como clase base para clases adicionales (hermanas, del mismo nivel).

### 053 [Polimorfismo](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20634320#announcements)

En tiempo de ejecución los objetos de una clases derivada, pueden ser tratados como objetos de una clases base (para métodos, colecciones o matrices).

### 054 [Bibliotecas de clases base de .NET](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20634422#announcements)

---

### 055 [Record](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/29994274#announcements)

Es otra manera de definir tipos. Se puede utilizar en lugar de clases o estructuras. Es un tipo por referencia. 
Es "similar" a una clase.
Para el almacenamiento de datos presentan una sintaxis mas concisa.

``` C#
    // Tipo por referencia.
    public record Pet1
    {
        //
    }
    // Tipo por valor.
    public record struct Pet2
    {
        //
    }
```

---
---

## - 09 Entrada / Salida - Manejo de archivos de texto

### 058 [Entrada / Salida en consola](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20634714#announcements)

La palabra reservada `using` ayuda en el manejo de objetos en memoria, asegurando que se eliminarán de forma correcta al terminar de ejecutar esa sección.

`SetIn` y `SetOut` redirecciónan la salida estandard de pantalla o archivo con `StreamReader` y `StreamWriter`. Con los métodos OpenText() y CreateText().
La lectura del archivo de produce de a una lectura por cada línea del archivo origen.

### 059 [Usando E/S en archivos](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20634746#announcements)

**Nota:** El simbolo `@` al comienzo de una cadena string, ayuda a omitir las secuencias de escape.

Tambien se puede leer un archivo en una sola pasada, con ReadAllText() y WriteAllText() para grabarlo.

---
---

## - 10 Rendimiento y gestión de memoria

### 061 [Tipos de valor vs tipos de referencia]()

#### Tipos por valor:

se alojan en la pila, para datos del tipo primitivo. No se modifican los datos originales, sino que se genera una "copia".

#### Tipos de referencia:

 se alojan en el Heap (Montón), para otros tipos de objetos y variables de tipo que no tienen una longitud determinada, como los string. En estos casos si se modifica los datos originales.
Tiene un menor rendimiento que los tipos de valor.

### 062 [Tipos de conversión - Implícita o de ampliación](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20937440#announcements)

No hay pérdida de información, pero puede haber pérdida de precisión.

### 063 [Tipos de conversión - Explícita o de restricción](https://www.udemy.com/course/aprende-a-programar-desde-cero-con-c-sharp-de-microsoft-dot-net/learn/lecture/20937444#announcements)

Puede producir una perdida de datos.


EconomyApp = https://twitter.com/EconomyApp?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor
americanas competencia de ML en Brasil.
Short Seller
SAMI debería llegr de 180 a 250
Oro cayó 4% en 3 días y NASDAQ subió, hay una divergencia.
Se compra oro cuando hay expectativa de infración.
Los bonos argentinos en dólares cayeron.
Se espera que la economía vuelva al nivel de crecimiento del final de 2021.
Del 10 al 20% de la cartera en Metales, para balancear la cartera.
Meta es un proyecto a 5 años.
