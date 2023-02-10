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
