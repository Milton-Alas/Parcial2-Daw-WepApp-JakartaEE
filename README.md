# Parcial2-Daw-WepApp-JakartaEE


Proyecto Parcial 2 - DAW135
Este proyecto es la solución al examen parcial 2 de la asignatura DAW135 (Desarrollo de Aplicaciones Web) en la Universidad de El Salvador. Es una aplicación web desarrollada con Jakarta EE 10, JSP, PrimeFaces y una base de datos PostgreSQL alojada en la nube en Neon.tech.

Configuración de la Base de Datos

Para configurar la conexión a la base de datos en Neon utilizando un pool de conexiones en Payara, sigue estos pasos:

En el servidor Payara, crea un nuevo pool de conexiones JDBC:

Abre la consola de administración de Payara.
Navega a “Recursos” > “Pools de conexión JDBC” > “Crear nuevo pool de conexiones JDBC”.
Configura el pool de conexiones con los siguientes valores:
Nombre del pool: NeonPool
Recurso del tipo: javax.sql.DataSource
Proveedor de recursos de datos: Postgres
En la pestaña “Propiedades adicionales”, agrega las siguientes propiedades:
ServerName: ep-restless-leaf-a5m23i1w-pooler.us-east-2.aws.neon.tech
DatabaseName: neondb
PortNumber: 5432
UseSSL: false
User: neondb_owner
Password: n5SYpDr6wGzE
Guarda el pool de conexiones.
Crea un nuevo recurso JDBC:

Navega a “Recursos” > “Recursos JDBC” > “Crear nuevo recurso JDBC”.
Selecciona el pool de conexiones creado anteriormente (NeonPool).
Asigna un nombre JNDI al recurso (por ejemplo, jdbc/neonDB).
Guarda el recurso JDBC.
Abre el archivo persistence.xml ubicado en src/main/resources/META-INF/persistence.xml.

Busca la sección <properties> dentro de la configuración del <persistence-unit>.
Actualiza la propiedad javax.persistence.jdbc.url con el nombre JNDI del recurso JDBC creado:
```xml

Ejecutar el Proyecto
Asegúrate de tener instalado Java Development Kit (JDK) y un servidor de aplicaciones como Payara, GlassFish o WildFly.
Clona este repositorio en tu máquina local.
Importa el proyecto en tu IDE preferido (por ejemplo, NetBeans o Eclipse).
Configura el servidor de aplicaciones con la conexión a la base de datos en Neon siguiendo los pasos mencionados anteriormente.
Despliega el proyecto en el servidor de aplicaciones.
Accede a la aplicación web en tu navegador utilizando la URL correspondiente.
Contribución
Si deseas contribuir a este proyecto, puedes crear un fork, realizar tus cambios y enviar una solicitud de extracción (pull request).

Integrantes del equipo
Milton Obed Alas Hernandez - AH09062
Lilian Sofia Tejada Villatoro - TV22008
David Alfredo Parada Mendoza - PM13119
