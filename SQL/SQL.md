Introudccion a SQL

    Es un lenguaje declarativo de muy alto nivel desarrollo por IBM una empresa que dio nombre a las siglas SQL
    (Sistema de Datos y Lenguaje de Consulta Estructurado)

    Esta basado en algebra y calculo relacional asi teniendo fundamentacion matematica.

    Modelo relacional           Representación lógica (SQL)
        
        Relación                          Tabla

        Tupla                             Fila

        Atributo                          Columna




    Pueden englobarse en dos funciones:

        Lenguaje de definicion de datos (Data Definition Language, DDL)
            Crea elimina y modifica objetos (tablas, vistas, indices..)


        Lenguaje de manipulacion de datos (Data Manipulation Laguage, DML)
            Insercion, actualización, consulta y borrado de datos.



        A pesar de estar estas dos tb existe otra categoria que es para la administracion de datos:

        Lenguaje de control de datos (Data Control Language, DCL)




    Ejemplo de trabajo:


        Una asosiacion cervecera nos ha pedido que modelemos su base de datos. Tenemos que almacenar el identificador, nombre y caracteristicas de la cerveza
        asi como su fabricante, del que de ese fabricante tenemos que sacar el nombre, correo y telefono.

        También hay que almacenar el nombre, dirección y número de licencia de los bares y el nombre, dirección y teléfono de los socios.
        De igual forma hay que almacenar qué cervezas le gustan a cada socio, qué cervezas vende cada bar, el precio al que cada uno de
        ellos la vende.


        ![alt text](/SQL/imagenes/image.png)



    Socio (ID_socio, Nombre, Direccion, Telefono)

    Bar (Licencia, Nombre, Direccion)

    Fabricante (ID_fabricante, Nombre, Telefono, Direccion)

    Cerveza (ID_cerveza, Nombre, Caracteristicas, ID_fabricante)

    Gusta (ID_socio, ID_cerveza)

    Vendedor (Licencia_bar, ID_cerveza, Precio)




Esquema SQL:

    Permite agrupar elementos pertenecientes a la misma aplicacion de una BD (Base de Datos).

    Se compone de:

        Tablas.
        Restricciones.
        Vistas.
        Otras Estructuras.

    Para MYSQL un esquema es sinónimo de base de datos.






CREATE SCHEMA AND USE:

    Lo primero que hay que hacer es crear el esquema sobre el que trabajaremos.

        CREATE SCHEMA nombre_esquema;

    Como hemos mencionado MYSQL usa esquemas y BD como sinónimos.

        CREATE DATABASE nombre_base_de_datos;


    Antes de trabajar siempre tenemos que decir sobre que esquema o BD queremos trabajar.

        USE nombre_esquema;


    IMPORTANTE -> Todos los comandos en SQL acaban en ; y los comentarios van procedidos de #



CREATE TABLE:

    El comando CREATE se usa para crear tablas y mas estrcuturas.

    Al crear una tabla hay que especificar el nombre, los atributos, los tipos(dominios) de las columnas (atributos) y sus restricciones de integridad.


    CREATE_TABLE nombre_tabla(
        columna_1 tipo [UNIQUE][NOT NULL][DEFAULT valor],
        ....

        columna_n tipo [UNIQUE][NOT NULL][DEFAULT valor],

        PRIMARY_KEY (columna_i),

        FOREIGN_KEY (columna_i)REFERENCES tabla_a (PK_tabla_a),
        ...

        FOREIGN KEY (columna_k) REFERENCES tabla_b (PK_tabla_b)
    );




    Modificadores principales de los atributos de una tabla:

        PK: Clave Primaria.
        NN: Not null.
        UQ: Unique (valores diferentes siempre, pero puede ser nulo).
        B: Columna de binarios.
        UN: Tipo de dato sin signo (no numeros negativos).
        ZF: Zero fill( para tipos numericos, rellena con cero a la izquierda).
        AI: Auto increment (para tipos numéricos, genera valores incrementando respecto al previo).
        G: Columna que genera su valor en base a otras columnas dada una expresion.


    Ejemplo de tabla generada para calcular hipotenusa en base a dos lados de triangulos de un triangulo

    ![alt text](/SQL/imagenes/image-1.png)

