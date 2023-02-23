# Curso Básico de Programación con C#

Muy muy básico, lo dejo porque yá lo escribí.

## 8 - Palabra reservada var

Las variables del tipo implícito se deben inicializar.

``` c#
var ladoA = 1.1

```

Para indicar que el formato es double, aunque en la asignación no tiene decimales.

``` c#
var radio = 0d
```

Nombres: Las variables deben comenzar con minúscula y la constantes con mayúscula.

## 16 - Ciclo while

``` c#
while (condition)
    {
        ...
    } 

// Do While

do
    {
        ...
    } while (condition)
```

## 18 - Ciclo for
``` c#
for (int i = 4; i < valor; step)
    {
        ...
    } 

// Do While

do
    {
        ...
    } while (condition)
```


----

## Formas de incializar un objeto.

A partir de C# 8.0  
Son indistintas.

Por lo general
``` c#
Car myCar = new Car();
```

El tipo lo infiere de lo que está a la derecha
``` c#
var myCar = new Car();
```

Otr forma
``` c#
Car myCar = new();
```

