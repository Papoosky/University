![[Pasted image 20230920205422.png]]

### 1. Compute Engine
- Permite a los usuarios ejecutar máquinas virtuales (VM) en la infraestructura global de Google. Estas VM pueden ejecutarse en una variedad de sistemas operativos y se pueden configurar según las necesidades de recursos de computación, memoria y almacenamiento.
- **Cuándo Usarlo:** Deberías considerar Compute Engine cuando necesitas un control completo sobre la máquina virtual subyacente y el sistema operativo, o cuando estás migrando aplicaciones existentes que requieren configuraciones personalizadas.
- **Escenario Típico:** Aplicaciones monolíticas, bases de datos tradicionales, cargas de trabajo personalizadas, aplicaciones que requieren acceso a nivel de sistema operativo.
### 2. Kubernetes
- Permite a los usuarios desplegar, gestionar y escalar contenedores de Docker de manera eficiente.
-  **Cuándo Usarlo:** GKE es una excelente opción cuando deseas orquestar y gestionar contenedores en un entorno altamente escalable, especialmente para aplicaciones basadas en microservicios. También para desarrollo hibrido y multicloud 
- **Escenario Típico:** Aplicaciones basadas en microservicios, contenedores de Docker, implementaciones altamente escalables, gestión de clústeres.
### 3. Cloud Run
- Servicio completamente administrado que permite ejecutar aplicaciones en contenedores sin necesidad de administrar la infraestructura subyacente. Se basa en el estándar de contenedores de Docker y permite la escalabilidad automática según la demanda.
- **Cuándo Usarlo:** Cloud Run es ideal para aplicaciones web y microservicios que requieren escalabilidad automática y que se pueden empaquetar en contenedores de Docker.
- **Escenario Típico:** Aplicaciones web, API, microservicios, aplicaciones sin servidor, despliegue rápido, escalabilidad automática según la demanda.
### 4. Cloud Functions
- Google Cloud Functions es un servicio de cómputo sin servidor que permite a los desarrolladores ejecutar código en respuesta a eventos en la nube sin preocuparse por la administración de servidores.
- **Cuándo Usarlo:** Cloud Functions se utiliza para crear aplicaciones y servicios altamente escalables y sin servidor. Puede usarse para automatizar tareas, procesar datos, responder a eventos en tiempo real y más.
- **Escenario Típico:** Automatización, conexión con sistemas o APIs externas

-----------------------###########-------------------------------

![[Pasted image 20230921175039.png]]

## 1. Object
- ### Cloud storage:
	- Para cualquier tipo de data. Almacenamiento de  cualquier tipo y cantidad de datos durante cualquier duración y recupérelos con tanta frecuencia como sea necesario. 
	- Datos no estructurados, archivos, imágenes, videos, copias de seguridad. Se almacenan en contenedores llamados cubos
## 2. Block
- ### Persistent Disk:
	- Proporciona discos virtuales para máquinas virtuales. Se pueden adjuntar y utilizar con instancias de Compute Engine para almacenar datos y sistemas de archivos. 
	- Discos para VMs
	- Datos read-only compartidos entre VMs
	- Almacenamiento de base de datos
- ### Local ssd:
	- Almacenamiento temporal y de alto rendimiento que se encuentra directamente en la máquina virtual. Los datos no son persistentes y se borran cuando la maquina virtual se detiene o se elimina 
	- Rendimiento extremadamente rápido para aplicaciones que requieren alta velocidad de lectura/escritura
	- Disco de memoria virtual de aplicación
	- Media rendering
## 3. Filestore
- ### Filestore:
	- Servicio de almacenamiento gestionado por GCP. Proporciona sistemas de archivos compativles con NFS (Network File System) 
	- Útil para aplicaciones que requieren sistemas de archivos compartidos entre instancias de máquinas virtuales como aplicaciones de analisis de datos o desarrollo de software
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
- Ofrece un acceso rápido a los datos y es adecuada para datos a los que se accede con frecuencia 
- Se utiliza para datos activos que se acceden con regularidad, Contenido web, streaming, aplicaciones en tiempo real 
### 2. Nearline Storage
- Diseñada para datos que se acceden con menos frecuencia pero que aún necesites tener disponibles rápidamente 
- Copias de seguridad, archivos de registro, backups, disaster recovery.
### 3. Coldline Storage
-  Datos de acceso muy infrecuentes
- Ideal para copias de seguridad, registros de auditoría
### 4. Archive Storage
- Datos almacenados aquí tienen el acceso más lento y pueden tardar varias horas en recuperarse
- Se usa para datos que es altamente improbable que necesites recuperar con frecuencia
- Cumplimiento de normativas, archivos históricos.

![[Pasted image 20230921184756.png]]

-----------------------###########-------------------------------

![[Pasted image 20230921184853.png]]
### 1. **GCS Transfer Tools (Herramientas de Transferencia de GCS):**
- Son un conjunto de herramientas y utilidades proporcionadas por Google Cloud Storage (GCS) para facilitar la transferencia de datos a GCS. Incluyen herramientas como `gsutil`
- Son versátiles y se pueden utilizar en una variedad de casos. Son útiles para transferir datos a GCS desde servidores locales, otros sistemas de almacenamiento en la nube, servicios en línea, etc. También son útiles para automatizar tareas de transferencia y manipulación de datos.
- Para pequeñas transferencias de pocos TBs
### 2.**Transfer Service (Servicio de Transferencia):**
- Servicio gestionado que permite programar y automatizar transferencias de datos regulares desde ubicaciones fuera de Google Cloud hacia Cloud Storage. Proporciona una interfaz de usuario para configurar y administrar las transferencias.
- Transferencia en línea a gran escala
- Transferencia desde on-premises o desde otros servicios de nube
### 3.**Transfer Appliance (Appliance de Transferencia):**
- Solución física proporcionada por Google Cloud para transferir grandes cantidades de datos de manera rápida y eficiente desde ubicaciones locales a la nube. Los clientes cargan sus datos en el appliance y luego se envía a Google para la carga en GCS.
- Es útil cuando tienes una gran cantidad de datos que transferir y la velocidad de transferencia por internet es limitada o poco práctica. Es adecuado para migraciones masivas de datos o cuando es necesario realizar una primera carga de datos en la nube.
### 4. **BigQuery Data Transfer Service (Servicio de Transferencia de Datos de BigQuery):**
- Permite la ingestión programada de datos desde fuentes externas directamente a BigQuery, el servicio de análisis de datos de Google Cloud.
- Se utiliza para automatizar la ingestión de datos desde fuentes externas a BigQuery, lo que facilita el análisis y la visualización de datos en tiempo real. Es útil para la creación de paneles de control, análisis de registros, seguimiento de eventos y más.
- Data desde SaaS y aplicaciones de terceros

-----------------------###########-------------------------------

![[Pasted image 20230921200106.png]]

## Relational

### Cloud SQL
- Servicio de bases de datos relacionales completamente administrado que admite bases de datos MySQL, PostgreSQL y SQL Server. Google se encarga de la administración, el mantenimiento y las copias de seguridad, lo que facilita el despliegue y la gestión de bases de datos relacionales.
- Se usa en aplicaciones web, aplicaciones empresariales, móviles. ERP, CRM, SaaS. 
### Cloud Spanner
+ Base de datos global distribuida y completamente administrada que combina las ventajas de las bases de datos relacionales y la escalabilidad horizontal. Proporciona alta disponibilidad y coherencia global, lo que lo hace adecuado para aplicaciones globales en tiempo real.
+ Aplicaciones financieras, comercio electrónico, gaming
### Bare Metal
- Utilizar máquinas virtuales en modo "bare metal" (metal desnudo) para instalar y configurar tu propia base de datos relacional en una máquina virtual sin virtualización. Esto te brinda un control total sobre la configuración de la base de datos.
- Legacy aplications, 

