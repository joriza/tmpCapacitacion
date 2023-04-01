- [Windows form c# y SQL Server](#windows-form-c-y-sql-server)
    - [01. Preparación del proyecto](#01-preparación-del-proyecto)
    - [02. Diseño minimo de los formularios](#02-diseño-minimo-de-los-formularios)
    - [03. Creación de la Base de Datos](#03-creación-de-la-base-de-datos)
    - [04. Acomodando componentes de los formularios](#04-acomodando-componentes-de-los-formularios)
    - [05. Terminar de acomodar componentes de formularios](#05-terminar-de-acomodar-componentes-de-formularios)
    - [06. Crear clase EmpleadosBLL](#06-crear-clase-empleadosbll)
    - [07. Recolectar informacion de un formulario](#07-recolectar-informacion-de-un-formulario)
    - [08. Conectando a la base de datos](#08-conectando-a-la-base-de-datos)
    - [09. Mejorando clase, conexion a base de datos](#09-mejorando-clase-conexion-a-base-de-datos)
    - [10. Insertar Datos en Tabla Departamentos](#10-insertar-datos-en-tabla-departamentos)
    - [12. Definir método Agregar para DepartamentosDAL](#12-definir-método-agregar-para-departamentosdal)
    - [13.Modificando metodo agregar](#13modificando-metodo-agregar)
    - [14. Pablar DataGridView Departamentos](#14-pablar-datagridview-departamentos)
    - [15. Poblar DataGridView Departamentos Parte 2](#15-poblar-datagridview-departamentos-parte-2)
    - [16. Recuperar informacion seleccionada en el DataGridView](#16-recuperar-informacion-seleccionada-en-el-datagridview)
    - [17. Eliminar registro (Departamentos)](#17-eliminar-registro-departamentos)
    - [18. Modificar registro (Departamentos)](#18-modificar-registro-departamentos)
    - [19. Modificar Interface Gráfica Formulario Departamentos](#19-modificar-interface-gráfica-formulario-departamentos)
    - [20. Consulta a la base de datos con parámetros.](#20-consulta-a-la-base-de-datos-con-parámetros)
    - [21. Desactivar algunos componentes del Formulario](#21-desactivar-algunos-componentes-del-formulario)



# [Windows form c# y SQL Server](https://www.youtube.com/watch?v=cysQEFvYoE0&list=PLSuKjujFoGJ3JzIbDs4hzVq8pfthRgAU-)

[Basado en:](https://download.microsoft.com/download/2/2/1/221AD022-E701-488F-B070-7A0B87DFE789/Guia_Arquitectura_N-Capas_DDD_NET_4_(Borrador_Marzo_2010).pdf)

Winform 
Capas en Carpetas
SQL DbFirst
ADO DATA PROVIDER
SQL Queries  
Solucion: AdminEmpleados
Comienza con la interface gráfica


### 01. [Preparación del proyecto]()

BLL - Busines Logic Layer
DAL - Data Access Layer
PC - Presentation Layer

### 02. Diseño minimo de los formularios

### 03. Creación de la Base de Datos

Creado desde SQL Server

En el diagrama se crearon las relaciones entre tablas, llaves primarias, autonumeracion.  
Se activó acción en cascada para insert y update.

### 04. Acomodando componentes de los formularios

### 05. Terminar de acomodar componentes de formularios

Crear clase DepartamentoBLL

### 06. Crear clase EmpleadosBLL

Boton Departamento Agregar

### 07. Recolectar informacion de un formulario

FrmDepartamentos.

### 08. Conectando a la base de datos

Prueba de conexion a base de datos.
~~~ C#
    public bool PruebaConectar()
    {
        try
        {
            using (var con = new SqlConnection("Data Source=HCI-NOTE227\\SQLEXPRESS;Initial Catalog=dbSistema_2;Integrated Security=SSPI;"))
            {
                var cmd = new SqlCommand();

                cmd.CommandText = "Select * from Empleados";
                cmd.Connection = con;
                con.Open();
                cmd.ExecuteNonQuery();
                con.Close();
            }

            return true;
        }
        catch (Exception)
        {
            return false;
    0    }
    }
~~~

> Es una buena práctica que la cadena de conexion esté en el archivo App.config.

[Apunte con diversos Connection Strings: ](www.connectionstrings.com/sql-server)

### 09. Mejorando clase, conexion a base de datos

### 10. Insertar Datos en Tabla Departamentos

Se insertan datos fijos, para verificar que esté insertando datos en la base de datos.

### 12. Definir método Agregar para DepartamentosDAL

### [13.Modificando metodo agregar](https://www.youtube.com/watch?v=D7YuRPW9xmc&list=PLSuKjujFoGJ3JzIbDs4hzVq8pfthRgAU-&index=14)

Ahora graba nombre de departamento en la base de datos.  
el id es autonumérico, por lo tanto lo genera solo el motor sql server. 

### 14. Pablar DataGridView Departamentos

### 15. Poblar DataGridView Departamentos Parte 2

### 16. Recuperar informacion seleccionada en el DataGridView

### 17. Eliminar registro (Departamentos)

### 18. Modificar registro (Departamentos)

### 19. Modificar Interface Gráfica Formulario Departamentos

Llenar grilla, colocar en un método  
Agregar iconos a los botones.

### 20. Consulta a la base de datos con parámetros.

~~~ C#
    public bool Agregar(DepartamentoBLL oDepartamentosBLL)
    {
        var cmd = new SqlCommand("INSERT INTO Departamentos VALUES (@Departamento)");
        cmd.Parameters.Add("@Departamento", SqlDbType.VarChar).Value = oDepartamentosBLL.Departamento;
        return conexion.EjecutarComandoSinRetornoDatos(cmd);
    }
~~~
Método que llama el primer método.
~~~ C#
        public bool EjecutarComandoSinRetornoDatos(SqlCommand Comando)
        {
            try
            {
                using (SqlCommand cmd = Comando)
                {
                    cmd.Connection = this.EstablecerConexion();
                    con.Open();
                    cmd.ExecuteNonQuery();
                }

                return true;
            }
            catch
            {
                return false;
            }
        }
~~~

### 21. Desactivar algunos componentes del Formulario

Segun la tarea que se esté realizando, para minimizar errores de uso.

