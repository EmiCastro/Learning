# Fundamentos de Bases de Datos

## Teoría general de Bases de Datos

- Las Bases de Datos surge de la necesidad de tener almacenados de forma eficiente los datos de nuestro proyecto. Anteriormente, los datos se almacenaban en papel (algunas empresas, por temas regulatorios aún mantienen este sistema). El papel tiene el limitante temporal que implica hacer búsquedas y consultas en grandes volúmenes de archivos físicos. Tener Bases de Datos ha permitido tener mejor accesso y control a los mismos.
- **Los datos no son información.** Sólo en el momento que creamos un reporte que contenga ciertos datos, con un criterio particular, éstos se convierten en información.
- **DBMS** = Data Base Management System o **SGBD** Sistemas de Gestión de Bases de Datos.

### Propósito general de las Bases de Datos
- **1950-1960**: Máquinas tabuladoras, tarjetas perforadas y cintas magnéticas.
- **1960-1979**: Modelos jerárquicos, discos duros, modelo de data relacional, transacciones en tiempo real.
- Un disco duro tiene **información persistente**, es decir, que perdura en el tiempo.
- **1970-1980**: SQL, Sistemas SQL comerciales, bases de datos paralelas y distribuidas, bases de datos orientadas a objetos.
- **SQL es un estándar**, la mayoría de los comandos básicos deben funcionar en cualquier tipo de base de datos que sea SQL (MariaDB, MySQL, etc).
- **1980-1990**: Data mining, data warehouse, e-commerce.
- **2000-actualidad**: XML, administración automatizada, analytics, big data, No SQL, InMemory, Scale Out, Systems of Engagement.


### Tipos de Bases de Datos y sus aplicaciones en la industria
- Las **Bases de Datos** se pueden dividir en:
    - **Bases de Datos Relacionales**
    - **Bases de Datos no Relacionales**
- Bases de Datos Relacionales empresariales (más importantes)
    - **DB2**
    - **SQL Server**
    - **Oracle**
- Algunas **Bases de Datos Relacionales** comunes:
    - **MariaDB**: Es una distribución de BD que deriva de MySQL.
    - **Redis**: Una base de datos que en la actualidad se trabaja mucho.
    - **neo4j**: Es una base de datos basada en nodos. Está centrada en grafos y nos permite encontrar relaciones entre objetos. Muy útil en e-commerce.
    - **Cassandra**: Es una base de datos muy importante del proyecto Apache. Trabaja con grandes volúmenes de datos.
    - **MongoDB**: Es una base de datos NoSQL que se basa en trabajar en varias instancias aplicando el principio de "Divide y vencerás".
    - **PostgreSQL**: Esta es una BD comunitaria pero tiene una versión enterprise con soporte.


### Visión general de los datos

**¿Qué es un dato?**
Un dato es algo que nos va a permitir describir un objeto. Ese objeto global lo vamos a poder llamar "Entidad". Una entidad puede estar llena de datos.

**Entidad**: Abstracción de un objeto. Tiene características.
**Relación**: Cómo se comportan los objetos con respecto a otros objetos.

Existen **3 niveles de abstracción en las bases de datos:**
- **Conceptual**: Se tiene que empezar a modelar una base de datos, dependiendo de lo que se quiere hacer, basado en los conceptos de "entidad" y "relación".
- **Lógico**: El diagrama lógico nos va a resolver ciertas dudas de consistencia, para evitar crear redundancias o sinsentidos en nuestra base de datos.
- **Físico**: Esto es, finalmente, cómo lo va a ver la base de datos. Es la implementación en el lenguaje.


### Tipos de Datos

Igual que en cualquier lenguaje de programación, existen **variables** en las bases de datos:
    - **Caracteres**: Pueden ser desde letras hasta caracteres especiales.
    - **Numérico**: Del 0 al 9 pero con una longitud especial.
    - **Varchar**: Caracteres con un formato más variable.
    - **Imagen**: Para manejar imagenes no se recomienda BD relacional, se recomiendan **Mongo SQL**, el **concepto HDFS con Hadoop** y **JPFS**
    - **Moneda**: Esto facilita todo si se trabaja con diferentes denominaciones.
    - **Texto**: Variables que tienen mayor tamaño que un char o que un varchar.
    - **Bit**: Es un booleano. Se representa con 1 o 0, ó con true o false.
    - **Decimal**.

**Esquema** = Es la estructura lógica que va a tener una Base de Datos.
**Instancia** = Contenido de partículas que tiene una base de datos en un instante de tiempo.

¿Qué debemos esperar para modelar una base de datos?
    - Los datos.
    - La relación que existe entre los datos.
    - Restricciones de los datos.

Existen 3 cosas para poder hacer la descripción de una base de datos:
    - **DML** = Data Manipulation Language o Lenguage de Manipulación de Datos.
    - **DDL** = Data Definition Language o Lenguage de Definición de Datos.
    - **SQL** = Structured Query Language o Lenguage de Consulta Estructurada.

**Otros tipos de bases de datos**:
    - Bases de datos Relacionales
    - Basadas en Objetos Relacionales
    - XML
    - NoSQL
    - In-Memory


### Diferentes tipos de Bases de Datos

**Características de Bases de Datos SQL:**
    - Es un lenguaje **estructurado**.
    - Tiene un esquema de **tablas**.
    - Tiene integración con otros tipos de archivos.
    - Tiene indexación por medio de árboles.
    - Ejemplos: PostgreSQL, MariaDB, MySQL.

**Características de Bases de Datos NoSQL:**
    - Se puede trabajar con un lenguaje estructurado o uno no estructurado.
    - Tiene diferente tipo de indexación. Se utiliza normalmente JSON.
    - Tiene un crecimiento horizontal (Scale out).
    - Ejemplos: MongoDB, Cassandra.

**Características de Bases de Datos Analíticas y de Big Data:**
    - Son de lenguaje no estructurado.
    - Tiene integración de muchos sistemas.
    - Tiene integración también a sistemas tradicionales y sistemas de engagement.
    - Aplica el principio "Divide y Vencerás".
    - Se basa en esquemas Scale out.
    - Crecimiento horizontal.
    - Ejemplos: Spark, Hadoop, Hortonworks.

**Características de Bases de Datos basadas en aceleración:**
    - Normalmente basadas in Memory.
    - Uso de aceleradores como GPU, flash cards, FPGAs.
    - Tienen estructuras diferentes, por ejemplo, basadas en nodos.
    - Uso frecuente de ambientes empresariales productivos y de datawarehouse.
    - Ejemplos: redis, neo4j, kinetica.


**Formas de usos en las bases de datos:**
    - On premise: la instalo en mi máquina y no necesito gran estructura. Puede ser open source o de formato empresarial.
    - Licenciadas por cores o sockets.
    - Licenciamiento modular. Se paga por funcionalidades o módulos para necesidades diferentes.
    - Pago por uso a través de SAAS ó PAAS.
    - Suscripción de nodos de cómputo.


## Bases de datos Relacionales
### ¿Qué es una Entidad?

**Entidad**: Es una abstracción del mundo real.
**Modelo Barker**: Aquí las entidades se representan como una caja con atributos, que pueden ser obligatorios u opcionales.

[Barker's Notation](http://www.vertabelo.com/blog/technical-articles/barkers-erd-notation)

**Recomendación**
El formato para trabajar con los ID debe ser **number**. No siempre podrá ser así pero es lo más recomendable.

### ¿Qué es una Relación?

Para definir una **Relación** tenemos que tener en cuenta los siguientes puntos:
    - **La obligatoriedad**. Ésta se denota con una línea contínua.
    - **Opcional**. Se representa con una línea punteada.
**Datos importantes**:
El símbolo con el que representamos la relación "de uno a muchos" es con la llamada "pata de gallo", que gráficamente es una línea contínua con dos líneas a 45 grados por cada lado.
```
0 - 1 ----------- (cero a uno: es obligatorio pero solo se puede tener uno)
1 - 1 ___________ (uno a uno: es obligatorio y solo se puede tener uno)
0 - M ----------≡ (cero a muchos: no es obligatorio y se puede tener muchos)
1 - M __________≡ (uno a muchos: es obligatorio y se puede tener muchos)
M - M ≡---------≡ (muchos a muchos: no es obligatorio y se puede tener muchos)

### Características o datos de una Entidad

**Índices**
Se recomienda que sean de tipo **number** porque estos timpos de datos son más **rápidos** de encontrar por medio de una búsqueda, ya que solo hay 10 posibilidades (0 a 9) de comparación por caracter.

### Llaves
- Las llaves nos dan acceso a los datos de una entidad. Su notación es la del numeral **#**.
- Las llaves tienen que ser **irrepetibles y obligatorias**, por lo tanto el ID puede ser una llave.
- Una llave puede ser **compuesta**.
- Las llaves **foráneas** son referencias a llaves primarias de otras tablas. Van a estar en nuestra tabla y nos permiten acceder a la tabla de la cual sean llave primaria.
- Las llaves son fundamentales porque son obligatoriamente **índices**, los cuales permiten encontrar los datos cuando se necesitan de una forma rápida y ordenada.

// WIP - TODO: finish this doc.
