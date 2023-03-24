- [Desarrolla Sistemas en C# .Net - 4 capas con SQL Server](#desarrolla-sistemas-en-c-net---4-capas-con-sql-server)
  - [Sec.02 - Definiendo y creando Base de Datos](#sec02---definiendo-y-creando-base-de-datos)
  - [Sec.03 - Arquitectura del proyecto](#sec03---arquitectura-del-proyecto)
    - [06. Definicion de BD con script SQL](#06-definicion-de-bd-con-script-sql)
  - [Sec.04 - Acceso a Datos](#sec04---acceso-a-datos)
    - [08. Creando solucion en capas](#08-creando-solucion-en-capas)
    - [09. Conexion a la base de datos](#09-conexion-a-la-base-de-datos)
    - [10. Alternativa de conexion a la base de datos.](#10-alternativa-de-conexion-a-la-base-de-datos)
  - [Sec.05 - Mantenimiento Crud - Entidad Categoría](#sec05---mantenimiento-crud---entidad-categoría)
    - [11. Capa entidades - Entidad Categoría](#11-capa-entidades---entidad-categoría)
    - [12. Capa Datos - Creando procedimientos almacenados](#12-capa-datos---creando-procedimientos-almacenados)
    - [13. Capa Datos - Clase Categoria](#13-capa-datos---clase-categoria)
    - [14. Capa Negocio - Clase Categoria](#14-capa-negocio---clase-categoria)
    - [15. Capa Presentación - Clase Categoria](#15-capa-presentación---clase-categoria)
    - [16. Capa Presentación - Opciones de Menú - Formulario de Mantenimiento](#16-capa-presentación---opciones-de-menú---formulario-de-mantenimiento)
    - [17. Capa Presentación - Entidad Categoria - Listar registros](#17-capa-presentación---entidad-categoria---listar-registros)
    - [18. Capa Presentación - Entidad Categoria - Buscar registros](#18-capa-presentación---entidad-categoria---buscar-registros)
    - [19. Capa Presentación - Entidad Categoria - Insertar registros, validaciones](#19-capa-presentación---entidad-categoria---insertar-registros-validaciones)
    - [20. Capa Presentación - Entidad Categoria - Actualizar registros](#20-capa-presentación---entidad-categoria---actualizar-registros)
    - [22. Capa Presentación - Entidad Categoria - Eliminar registros](#22-capa-presentación---entidad-categoria---eliminar-registros)
    - [23. Capa Presentación - Entidad Categoria - Activar/Desactivar registros](#23-capa-presentación---entidad-categoria---activardesactivar-registros)
  - [Sec.06 - Mantenimiento Crud - Entidad Articulo](#sec06---mantenimiento-crud---entidad-articulo)
    - [24. Capa Entidades - Entidad Articulo](#24-capa-entidades---entidad-articulo)
    - [25. Capa Entidades - Entidad Artículo - Procedimientos almacenados](#25-capa-entidades---entidad-artículo---procedimientos-almacenados)
    - [26. Capa Datos - Clase DArticulo](#26-capa-datos---clase-darticulo)
    - [26. Capa Negocio - Clase NArticulo](#26-capa-negocio---clase-narticulo)


# [Desarrolla Sistemas en C# .Net - 4 capas con SQL Server](https://www.udemy.com/course/desarrolla-sistemas-c-sharp-net-sql-server-4-capas-poo/learn/lecture/15481990?start=600#overview)

Winform  
SQL DbFirst  
Procedimientos almacenados  


## Sec.02 - Definiendo y creando Base de Datos

## Sec.03 - Arquitectura del proyecto

### 06. [Definicion de BD con script SQL](https://www.udemy.com/course/desarrolla-sistemas-c-sharp-net-sql-server-4-capas-poo/learn/lecture/15481990#overview)

9 Tablas relacionadas.
En el script indica clave primaria y autonumerico.  
Tambien las referencias a otras tablas relacionadas.  
Al definir los campos que relacionan tablas, no es necesario que tengan el mismo nombre, pero si el mismo tipo de dato.  

## Sec.04 - Acceso a Datos

### 08. Creando solucion en capas

Crea solucion vacía.  
Crea 4 proyectos que serán las capas.  
Agregar comunicacion entre las capas.

### 09. Conexion a la base de datos

www.connectionstrings.com/sql-server

### 10. Alternativa de conexion a la base de datos.

Desde un asistente de VS, con los datos que le pasamos, arma la cadena de conexión.  
Aunque parece que no lo vamos a usar, el asistente la agrega en el archivo App.config.  

## Sec.05 - Mantenimiento Crud - Entidad Categoría

### 11. Capa entidades - Entidad Categoría

Esta capa contiene una clase por cada tabla de la base de datos.  

### 12. Capa Datos - Creando procedimientos almacenados

### 13. Capa Datos - Clase Categoria

### [14. Capa Negocio - Clase Categoria](https://www.udemy.com/course/desarrolla-sistemas-c-sharp-net-sql-server-4-capas-poo/learn/lecture/15482044#overview)

Los métodos serán estáticos, porque en la capa presentación no se van a instanciar objetos de la clase NCategoria.  
No es necesario capturar excepciones, porque todas están en la capa Datos.  
Hasta aqui, la capa negocio, está actuando como si fuera solo un puente de comunicación entre la capa presentacion y capa datos.  
Pero se pueden insertar otro tipo de validaciones, como por ejemplo, que no se inserten datos duplicados en la base de datos.  En este caso, tambien con procedimientos almacenados, para cada situación que se quiera verificar.  
En el procedimiento almacenado de verificación, hay que hacer algunos pasos para poder utilizarlo adecuadamente.  
Y de esta forma toda la lógiica permanece en la capa Negocio.  

### 15. Capa Presentación - Clase Categoria

Se agrega el formulario principal MDI (Interface de Multiples documentos)  
En Program.cs se debe indicar que este será el primer formulario que se ejecutará.  

### 16. Capa Presentación - Opciones de Menú - Formulario de Mantenimiento

Crear Manu principal y sus opciones hijos.

### 17. Capa Presentación - Entidad Categoria - Listar registros

### 18. Capa Presentación - Entidad Categoria - Buscar registros

### 19. [Capa Presentación - Entidad Categoria - Insertar registros, validaciones](https://www.udemy.com/course/desarrolla-sistemas-c-sharp-net-sql-server-4-capas-poo/learn/lecture/15482088#overview)

Nota. El evento `BtnInsertar_Click` de `FrmCategoria`.  
Es un buen ejemplo para analizar como viajan parámetros.  
Tanto de ida como de vuelta. Sobretodo en las verificaciones.

### 20. Capa Presentación - Entidad Categoria - Actualizar registros

Como capturar datos de un DataGridView.  

### 22. Capa Presentación - Entidad Categoria - Eliminar registros

No me parece buena implementación en `BtnEliminar_Click`, tiene varios if anidados.  

### 23. Capa Presentación - Entidad Categoria - Activar/Desactivar registros

## Sec.06 - Mantenimiento Crud - Entidad Articulo

### 24. Capa Entidades - Entidad Articulo

### 25. Capa Entidades - Entidad Artículo - Procedimientos almacenados

### 26. Capa Datos - Clase DArticulo

### 26. Capa Negocio - Clase NArticulo

