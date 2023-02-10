# Notas del curso Udemy - Principios SOLID y Clean Code

## Nombres

### Variables:
Lower camelcase para nombres de variables.

### Funciones:
Deben representar acciones, pero abtenerse  de la implementación.  
Se construyen con verbo que representa la acciones seguida de un sustantivo.

### Clases:
Formados por un sustantivo o frases de sustantivos
UpperCamelCase

Que hace exactamente la clase
Como realiza cierta tarea la clase

Mas palabras no significa mejor nombre

## Usos de funciones

Argumentos es lo que se envía.
Parámetros es lo que se recibe.

Limitar a 3 parámetros posicionales.  
No deberían tener más de unas 20 líneas de código.  
Limitar el uso de else.  
Limitar el uso del condicional ternario.  

## Principio DRY

Simplemente es evitar tener duplicidad.
Simplifica las pruebas.
Ayuda a centralizar procesos.
Aplicar el principio DRY, usualmente lleva a refactorizar.

## Cap. 26 Herencia problemática (Buen ejemplo de como se puede complicar fácilmente el código)

Aplicar el principio de responsabilidad única con herencia, es casi imposible de hacer.

## 31 - Estructura recomendada de una clase

## 32 - Comentarios

Los comentarios deben ser la excepción y no la regla.
Solo comentar el por que se hace.
El como es el código.
El que no debería ser necesario si se hace auto explicativo.
No se debe comentar el código mal hecho, se debe rehacer el código.

## Cohesión y acoplamiento

Lo ideal es tener alta cohesión. y bajo acoplamiento.
La cohesión se refiere a lo que hace la clase (o módulo) puede hacer
La baja cohesión significaría que la clase realiza una gran variedad de acciones: es amplia, no se enfoca en lo que debe hacer.
La cohesión se refier a cuán relacionadas o dependientes son dos clases o módulos entre sí.
En bajo acoplamiento, cambiar algo importante en una clase no debería afectar a la otra.

## Otros olores honoríficos

Utilizar datos primitivos en lugar de pequeños objetos.
Lista larga de parámetros, intentar que no sean más de 4 parámetros en un método.
Cadena de mensajes. (A -> B -> C -> D)
El hombre del medio. (Que una clase solo llama a otra clase), es un subproblema de la cadena de mensajes.

## Principios Solid

Los 5 principios S.O.L.I.D. de diseño de software son:

### S – Single Responsibility Principle (SRP)

Responsabilidad única. (En clases y módulos). No es sinónimo de hacer solo una cosa.

### O – Open/Closed Principle (OCP)

Abierto y cerrado.
Las entidades deben estar abiertas para la extensión pero cerradas para la modificación.
Intentar tener la menor dependencia de librerías de terceros. O al menos que no hagan llamadas directa a métodos de la clase de terceros.  
Esos le logra utilizando una clase intermedia creada por uno mismo.  
C# No tiene herencia múltiple. Con lo cual es necesario apoyarse en las intertaces para poder hacer crecer la aplicación.

### L – Liskov Substitution Principle (LSP)

Sustitución de Liskov.

Los objetos dentro de un programa deben poderse reemplazar por subtipos de este sin alterar la lógica o el funcionamiento.

### I – Interface Segregation Principle (ISP)

Segregación de interfaz.
Los clientes no deberían estar obligados a depender de interfaces que no utilizan.    
Las clases no deben verse obligadas a utilizar métodos heredados que no utilizan. 

### D – Dependency Inversion Principle (DIP)

Inversión de dependencias.
Existen 3 tipos de inyección de dependencias.
- Por constructor.
- Por Propiedad.
- Por parámetro.
Es fundamental para poder aplicar la metodología TDD y poder hacer pruebas unitarias.  
(Ver patrón exagonal a ver si clarifica.)



## Notas adicionales

Platzi: Reveer cap. 8,10,12

Con clases abstractas o Interfaces
