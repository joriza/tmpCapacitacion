- [Generalidades de C#](#generalidades-de-c)
  - [Herencia y Polimorfismo](#herencia-y-polimorfismo)
  - [Modificadores de acceso](#modificadores-de-acceso)
  - [Interfaces](#interfaces)
  - [Operador IS](#operador-is)
- [Persistencia](#persistencia)
  - [Conexion Directa](#conexion-directa)
    - [ADO .NET DATA PROVIDER](#ado-net-data-provider)
      - [Cadena de Conexion](#cadena-de-conexion)
      - [Construccion de Conexion](#construccion-de-conexion)
    - [ADO DATA SET](#ado-data-set)
  - [Conexion con ORMs](#conexion-con-orms)
    - [EF](#ef)
    - [Dapper](#dapper)
- [Consola](#consola)
  - [Recorrer una lista](#recorrer-una-lista)
- [Escritorio](#escritorio)
  - [Diferencia entre castear y parsear](#diferencia-entre-castear-y-parsear)
- [Winform N Capas](#winform-n-capas)
  - [Capas en Proyectos o Carpetas](#capas-en-proyectos-o-carpetas)
- [Web](#web)
  - [ASP NET](#asp-net)
  - [ASP NET MVC](#asp-net-mvc)
  - [Blazor](#blazor)
    - [Lado Servidor](#lado-servidor)
    - [Lado Cliente](#lado-cliente)

# Generalidades de C#

## Herencia y Polimorfismo

Para poder sobreescribir un método, la clase base debe ser virtual. En el método de la clase hicha debe contener override. [Link](https://youtu.be/VfMxqlMiZPU?list=PL0kIvpOlieSN-PDnM2rHXdb3kib9njJaQ&t=235)

## [Modificadores de acceso](https://youtu.be/Fs2ii77at9s?list=PL0kIvpOlieSN-PDnM2rHXdb3kib9njJaQ)

- public: todos tienen permiso de acceso.
- static: El método necesita instanciarse se pertenecen al mismo namespace.  
- private: El método solo pueden usarse dentro de la misma clase.
- protected: El método solo se puede usarse en las clases derivadas(hijos) .  
- internal El método solo pueden accederse desde el mismo assembly (proyecto).

## [Interfaces](https://youtu.be/Yd5TBVTvfF4?list=PL0kIvpOlieSN-PDnM2rHXdb3kib9njJaQ)

Es un contrato que obliga a la clase que implementa la interface, a definir al menos todos los métodos que se encuentan en la interface.  
En la interface solo se definen los métodos, la implementación corresponde a la clase que la invoca.  
Las interfaces las podemos utilizar para aprovechar el polimorfismo. Ya qu el polimorfismo nos permite enviar un tipo a un método sin especificar que es lo que se vá a enviar.   

## Operador IS

Hay un tipo del cual todos los demas tipos heredan, que es `Object`.

# Persistencia

## Conexion Directa

### ADO .NET DATA PROVIDER

#### Cadena de Conexion

#### Construccion de Conexion

### [ADO DATA SET](https://youtu.be/bTKKbPVRKv4)

Es un intermedio entre ADO.NET y EF.  
El wizard consulta si le cadena de conexion se quiere colocar en App.config.  
Datatable es una tabla en memoria.

## Conexion con ORMs

### EF

### Dapper

# Consola

## Recorrer una lista

# Escritorio

## Diferencia entre castear y parsear

- Castear: De decimal a int.
- Parsear: De String a int.

# Winform N Capas

Es para separar responsabilidades como en MVC.   
No está muy claro como debe ser la separación de las capas.   
Cada capa puede ser una carpeta o un proyecto.  

## Capas en Proyectos o Carpetas

# Web

## ASP NET 

## ASP NET MVC

## Blazor

### Lado Servidor

### Lado Cliente


