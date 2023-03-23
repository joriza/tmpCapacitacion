# WinForm en Capas

- Crear Proyecto/Solucion Winform  
Que va a hacer las veces de la capa presentación

- Crear biblioteca de clases .Net Framework  
Que va a hacer las veces de la capa Datos  
Se puede eliminar class1.cs  
Agregar nuevo elemento: Datos / ADO NET  
Incluir las tablas con las que se vá a trabajar.  

- Crear biblioteca de clases .Net Framework  
Que va a hacer las veces de la capa ModeloNegocio  
Renombrar class1.cs por la entidad que se vá a trabajar.  

- Luego de creadas las capas:  
Agregar el contenido de la etiqueta `<connectionStrings>` de la capa datos, en las otras capas.  
Agregar paquete Nugget de EF en las otras 2 capas.  
Agregar referencia a Datos desde las otras 2 capas.  
Agregar referencia a ModeloNegocio en la capa Presentación.  





Esta parte es de otro video.

Indicar la bases de datos
Video 6/8

App.confirg
``` html
<connectionStrings>
    <add name="NorthWindCF" 
            connectionString=
                "Data Source=HCI-NOTE227\SQLEXPRESS; 
                initial catalog=NorthWindCF; 
                integrated Security=true; 
                MultipleActiveResultSets=true"
            providerName="System.Data.SqlClient"
    />
</connectionStrings>
```