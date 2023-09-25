![[Pasted image 20230920205422.png]]

### 1. Compute Engine (IaaS)
- <mark style="background: #FFF3A3A6;"> Permite a los usuarios ejecutar máquinas virtuales (VM)</mark> en la infraestructura global de Google. Estas VM pueden ejecutarse en una variedad de sistemas operativos y <mark style="background: #FFF3A3A6;">se pueden configurar según las necesidades de recursos de computación, memoria y almacenamiento.</mark>
- **Cuándo Usarlo:** Deberías considerar Compute Engine cuando necesitas un control completo sobre la máquina virtual subyacente y el sistema operativo, o cuando estás migrando aplicaciones existentes que requieren configuraciones personalizadas.
- **Escenario Típico:** Aplicaciones monolíticas, bases de datos tradicionales, cargas de trabajo personalizadas, aplicaciones que requieren acceso a nivel de sistema operativo.
### 2. Kubernetes (PaaS)
- <mark style="background: #FFF3A3A6;">Permite a los usuarios desplegar, gestionar y escalar contenedores de Docker de manera eficiente.</mark>
-  **Cuándo Usarlo:** GKE es una excelente opción cuando deseas orquestar y gestionar contenedores en un entorno altamente escalable, especialmente para aplicaciones basadas en microservicios. También para desarrollo hibrido y multicloud 
- **Escenario Típico:** Aplicaciones basadas en microservicios, contenedores de Docker, implementaciones altamente escalables, gestión de clústeres.
### 3. Cloud Run (PaaS)
- Servicio completamente administrado que permite <mark style="background: #FFF3A3A6;">ejecutar aplicaciones en contenedores sin necesidad de administrar la infraestructura subyacente</mark>. Se basa en el estándar de contenedores de Docker y permite la escalabilidad automática según la demanda.
- **Cuándo Usarlo:** Cloud Run es ideal para aplicaciones web y microservicios que requieren escalabilidad automática y que se pueden empaquetar en contenedores de Docker.
- **Escenario Típico:** Aplicaciones web, API, microservicios, aplicaciones sin servidor, despliegue rápido, escalabilidad automática según la demanda.
### 4. Cloud Functions
- Google Cloud Functions es un servicio de cómputo sin servidor que permite a los desarrolladores <mark style="background: #FFF3A3A6;">ejecutar código en respuesta a eventos en la nube sin preocuparse por la administración de servidores.</mark>
- **Cuándo Usarlo:** Cloud Functions se utiliza para crear aplicaciones y servicios altamente escalables y sin servidor. Puede usarse para automatizar tareas, procesar datos, responder a eventos en tiempo real y más.
- **Escenario Típico:** Automatización, conexión con sistemas o APIs externas

-----------------------###########-------------------------------

![[Pasted image 20230921175039.png]]

## 1. Object
- ### Cloud storage:
	- Para cualquier tipo de data. <mark style="background: #FFF3A3A6;">Almacenamiento de  cualquier tipo y cantidad de datos durante cualquier duración y recupérelos con tanta frecuencia como sea necesario. </mark>
	- Datos no estructurados,<mark style="background: #ABF7F7A6;"> archivos, imágenes, videos, copias de seguridad</mark>. Se almacenan en contenedores llamados cubos
## 2. Block
- ### Persistent Disk:
	- Proporciona<mark style="background: #FFF3A3A6;"> discos virtuales para máquinas virtuales</mark>. Se pueden adjuntar y utilizar con instancias de Compute Engine para almacenar datos y sistemas de archivos. 
	- Discos para VMs
	- Datos read-only compartidos entre VMs
	- Almacenamiento de base de datos
- ### Local ssd:
	- <mark style="background: #FFF3A3A6;">Almacenamiento temporal y de alto rendimiento que se encuentra directamente en la máquina virtual.</mark> Los datos no son persistentes y se borran cuando la maquina virtual se detiene o se elimina 
	- Rendimiento extremadamente rápido para aplicaciones que requieren alta velocidad de lectura/escritura
	- Disco de memoria virtual de aplicación
	- Media rendering
## 3. Filestore
- ### Filestore:
	- Servicio de almacenamiento gestionado por GCP. Proporciona sistemas de archivos compatibles con <mark style="background: #FFF3A3A6;">NFS</mark> (Network File System) 
	- Útil para aplicaciones que requieren<mark style="background: #FFF3A3A6;"> sistemas de archivos compartidos entre instancias de máquinas virtuales</mark> como aplicaciones de analisis de datos o desarrollo de software
	- Media processing
	- Genomics processing
	- Electronic Design Automation
	- Machine learning
	- Data Analytics 
	- Web content managment

-----------------------###########-------------------------------
## Cloud Storage 
![[Pasted image 20230921183028.png]]

### 1. Standard Storage
- Ofrece un <mark style="background: #FFF3A3A6;">acceso rápido a los datos y es adecuada para datos a los que se accede con frecuencia </mark>
- Se utiliza para datos activos que se acceden con regularidad, Contenido web, streaming, aplicaciones en tiempo real 
### 2. Nearline Storage
- Diseñada para datos que se acceden con menos frecuencia pero que aún necesites tener <mark style="background: #FFF3A3A6;">disponibles rápidamente </mark>
- <mark style="background: #ABF7F7A6;">Copias de seguridad, archivos de registro, backups, disaster recovery.</mark>
### 3. Coldline Storage
-  Datos de acceso <mark style="background: #FFF3A3A6;">muy infrecuentes</mark>
- <mark style="background: #ABF7F7A6;">Ideal para copias de seguridad, registros de auditoría</mark>
### 4. Archive Storage
- Datos almacenados aquí tienen el <mark style="background: #FFF3A3A6;">acceso más lento y pueden tardar varias horas en recuperarse</mark>
- Se usa para datos que es altamente improbable que necesites recuperar con frecuencia
- <mark style="background: #ABF7F7A6;">Cumplimiento de normativas, archivos históricos.</mark>

![[Pasted image 20230921184756.png]]

-----------------------###########-------------------------------

![[Pasted image 20230921184853.png]]
### 1. GCS Transfer Tools (Herramientas de Transferencia de GCS):
- Son un conjunto de herramientas y utilidades proporcionadas por Google Cloud Storage (GCS) para facilitar la transferencia de datos a GCS. Incluyen herramientas como `gsutil`
- Son versátiles y se pueden utilizar en una variedad de casos. <mark style="background: #FFB8EBA6;">Son útiles para transferir datos a GCS desde servidores locales, otros sistemas de almacenamiento en la nube, servicios en línea, etc.</mark> También son útiles para automatizar tareas de transferencia y manipulación de datos.
- <mark style="background: #FFB8EBA6;">Para pequeñas transferencias de pocos TBs</mark>
### 2. Transfer Service (Servicio de Transferencia):
- Servicio gestionado que permite programar y automatizar transferencias de datos regulares desde ubicaciones fuera de Google Cloud hacia Cloud Storage. Proporciona una interfaz de usuario para configurar y administrar las transferencias.
- <mark style="background: #FFB8EBA6;">Transferencia en línea a gran escala</mark>
- Transferencia desde on-premises o desde otros servicios de nube
### 3. Transfer Appliance (Appliance de Transferencia):
- Solución física proporcionada por Google Cloud para transferir <mark style="background: #FFB8EBA6;">grandes cantidades de datos de manera rápida</mark> y eficiente desde ubicaciones locales a la nube. Los clientes cargan sus datos en el appliance y luego se envía a Google para la carga en GCS.
- Es<mark style="background: #FFB8EBA6;"> útil cuando</mark> tienes una gran cantidad de datos que transferir y <mark style="background: #FFB8EBA6;">la velocidad de transferencia por internet es limitada o poco práctica.</mark> Es adecuado para migraciones masivas de datos o cuando es necesario realizar una primera carga de datos en la nube.
### 4. BigQuery Data Transfer Service (Servicio de Transferencia de Datos de BigQuery):
- Permite <mark style="background: #FFB8EBA6;">la ingestión programada de datos desde fuentes externas directamente a BigQuery</mark>, el servicio de análisis de datos de Google Cloud.
- Se utiliza para automatizar la ingestión de datos desde fuentes externas a BigQuery, lo que facilita el análisis y la visualización de datos en tiempo real. Es útil para la creación de paneles de control, análisis de registros, seguimiento de eventos y más.
- Data desde SaaS y aplicaciones de terceros

-----------------------###########-------------------------------

![[Pasted image 20230921200106.png]]

## Relational

### Cloud SQL
- Servicio de bases de datos relacionales completamente administrado que admite bases de datos MySQL, PostgreSQL y SQL Server. Google se encarga de la administración, el mantenimiento y las copias de seguridad, lo que facilita el despliegue y la gestión de <mark style="background: #FFB8EBA6;">bases de datos relacionales.</mark>
- Se usa en aplicaciones web, aplicaciones empresariales, móviles. ERP, CRM, SaaS. 
### Cloud Spanner
+ Base de datos global distribuida y completamente administrada que combina las ventajas de las bases de <mark style="background: #FFB8EBA6;">datos relacionales y la escalabilidad horizontal.</mark> Proporciona<mark style="background: #FFB8EBA6;"> alta disponibilidad y coherencia global</mark>, lo que lo hace adecuado para aplicaciones globales en tiempo real.
+ Aplicaciones financieras, comercio electrónico, gaming
### Bare Metal
- Utilizar máquinas virtuales en modo "bare metal" (metal desnudo) para instalar y configurar tu propia base de datos relacional en una máquina virtual sin virtualización. Esto te brinda un control total sobre la configuración de la base de datos.
- <mark style="background: #FFB8EBA6;">Legacy aplications </mark>

## Non-Relational
### Firestore
- Diseñada para almacenar y<mark style="background: #FFB8EBA6;"> consultar datos no estructurados o semiestructurados en una forma flexible y escalable.</mark>
- Ampliamente utilizado en el desarrollo de aplicaciones web y móviles, especialmente en aplicaciones que requieren una sincronización en tiempo real de datos entre dispositivos y una escalabilidad eficiente. Es una opción popular para aplicaciones de juegos, aplicaciones de colaboración en tiempo real, aplicaciones de comercio electrónico y muchas otras aplicaciones que requieren una base de datos flexible y confiable en la nube.

### Cloud Bigtable
- Está diseñado para manejar <mark style="background: #FFB8EBA6;">cargas de trabajo de datos masivos y de alto rendimiento</mark>, lo que lo hace ideal para aplicaciones que requieren un acceso rápido a grandes cantidades de datos estructurados, como análisis en tiempo real, sistemas de recomendación y aplicaciones de Internet de las cosas (IoT).
- Es ideal para almacenar grandes cantidades de datos de una sola clave con una latencia muy baja. Admite un alto rendimiento de lectura y escritura con una latencia inferior a milisegundos y es una fuente de datos ideal para las operaciones de MapReduce.

### Memory store
- Es una base de datos en <mark style="background: #FFB8EBA6;">memoria completamente administrada que se basa en la tecnología de Redis</mark>, un popular sistema de almacenamiento en caché y almacenamiento de datos en memoria.
- MemoryStore almacena datos en memoria RAM, lo que permite un <mark style="background: #FFB8EBA6;">acceso extremadamente rápido a los datos</mark>. Esto es útil para aplicaciones que requieren una alta velocidad de lectura y escritura de datos, como aplicaciones en tiempo real y sistemas de almacenamiento en caché.
- Ofrece la opción de habilitar la persistencia en disco para garantizar la durabilidad de los datos en caso de fallos.
- Memorystore es ideal para aplicaciones web y móviles, de juegos, de clasificación, sociales, de chat y de noticias.