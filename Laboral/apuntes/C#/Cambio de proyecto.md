# Cambio de proyecto, luego de SoundHound

## Es mi nuevo Team Leader

Nicolás Arroyo

## Paradigma presentado con mayor frecuencia 

MVP

## Paradigma a repasar

MVC Web en .Net con boostrap

## Bases de datos a repasar

pl sql y t sql

## Estado en el equipo en primer momento

Primero shadow  

## Realizan en MVC

usuarios grupos permisos

Si podemos agregar boostrap

MVC Web en .Net con boostrap

## Aveces se utiliza tambien

React y Angular

---

### Consultar

Diagramas en SQL Server

Crear usuario de BD en MSSMS

Modificar estructura en SQL, algunos cambios no adminte.

Consultar carga de horas de inglés.

Como si fuera Problema de Caché: entre SQL y VS  
    Parece ser al importar los Modelos con EF.  
        Eliminar Modelos 
        Eliminar en web.config la etiqueta connectionStrings y su contenido  
        y volver a intentar.  

Al crear controladores con EF marca error.  
    Solo hay que compilar.  
    Y volver a crear controladores con EF.  


Mejor usar DataBase First
Lo importante es el concepto del patron.


Que intento continuar.
Crear Los controladores y las vistas a mano.
    Llenar una lista desplegable a mano.

Que nos conviente continuar haciendo?
    Descoplar la parte del servicio.

    Ver que otra forma hay de hacer los pasos a mano.

    Todo con interfaces. 


- Net Framework o Net Core?
- EF o Dapper?
- Data Anotation o Fluent API?
- LinQ o Lambda?
- Ingles?

## 230223

Diferencia entre ViewBag y ViewData.
que es data context en .net
    Cual es el uso del DbContext


Algunos dataanotation que toma EF para mostrar en las vistas y que no sea el nombre del campo
Problemas con pasar una lista para mostrar.
Menu dentro de menu, pero hecho con bootstrap


MVC a mano con CodeFirst para crear la bd
usar sqlite, como para probar otro motor.
Maestro detalle con jscript. Se puede usar algo como datagrid?
    bostrap tiene como un datagrid.

RDL para reportes
    Reporting services


"Server=HCI-NOTE227\\SQLEXPRESS; Database=InventoryDb; Trusted_Connection=True"



### 230227

NetFramework MVC
AdoNet
JQuery
Bootstrap
Base de Datos para despues.


### 230302 Avances

Base de datos
    Aunque me recomendó no profundizar es una parte necesaria que algo mínimo se debe utilizar
        Tengo problemas para colocar campo identidad
        Al modificar la estructura
        En algunos casos no me ha quedado otra que eliminar la tabla
            lo llevo mejor con script de creacion, pero mejor no tener que regenerar.
            Caso campos que antes eran nulos y ahora no.

Data annotation personalizadas
    * en campos requeridos?
    Preguntar a manu como validó, utilizó otra cosa distinta a mi.
        Fluent validation

Modificar vistas
    Botones
        Tanto bootstrap como css
            Atento con la version de bootstrap, algunas cosas cambian mucho.

---
Error al intentar grabar un registro.
    Campo ID por identidad
        Era problema con la estructura de las clases que no se correspondía con las tablas físicas.
---

Logré completar y hacer funcional una lista desplegable.
    Ahora no funciona porque quedé a medio camino de hacerla con 2 niveles.
Inconveniente con 1 campo auxiliar en el método editar/Post. (Estado)
    Lo envía a la vista, como un campo físico más.
Al llenar el combo no me toma el registro 1 de ciudad, el primero es como que no existe.

LinQ con Query expresions o con métodos? Que conviene?
Un objeto anónimo de linq es un cursor?

Como tuve problemas para modificar estructura de BD en SSMS y al hacer pruebas necesito cambiar la estructura.
Una posibilidad era borrar y crear toda la BD ante cualquier cambio, lo cual es inficiente y muy propenso a errores.
Así que opté por practicar comandos para modificar estructura de BD

Que me conviene clase auxiliar o ViewContext¿

Como le indico que version de bootstrap voy a usar en el proyecto?

Descubrimientos recientes.
- [HttpPost] No es un data annotation, es un selector.
- Las ventajas del model binding.
- Outputcaché
- 
