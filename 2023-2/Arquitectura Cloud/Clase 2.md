### Docker vs Virtual Machines

- ![[Pasted image 20230920164448.png]]
- #### Máquinas virtuales:
	- Emulan sistemas operativos completos, lo que significa que incluyen un hipervisor, un sistema operativo huésped y luego los sistemas operativos invitados (VMs) dentro de ellas. Cada VM consume recursos considerables, como memoria y espacio de almacenamiento.
	- Proporcionan un alto nivel de aislamiento y seguridad, pero esto a menudo conlleva un mayor consumo de recursos.
	- Las VMs son más pesadas y lleva más tiempo crearlas y desplegarlas debido a su tamaño y complejidad.
- #### Docker
	- Docker utiliza la virtualización a nivel de contenedor, lo que significa que comparte el mismo kernel del sistema operativo anfitrión. Los contenedores Docker son ligeros y comparten recursos del sistema operativo, lo que los hace más eficientes en términos de uso de recursos en comparación con las VMs.
	- Los contenedores Docker son livianos y se pueden crear y desplegar rápidamente. Esto facilita la portabilidad y el escalamiento rápido de aplicaciones en entornos de nube.
- #### Importancia de Docker en arquitectura cloud
	- **Portabilidad:** Docker permite empacar una aplicación junto con todas sus dependencias en un contenedor. Esto significa que puedes desarrollar una aplicación en tu entorno local y luego ejecutarla sin cambios en cualquier entorno de nube compatible con Docker, lo que simplifica la implementación y reduce los problemas de compatibilidad.
	- **Escalabilidad:** Los contenedores Docker se pueden escalar fácilmente según las necesidades. Puedes aumentar o disminuir el número de contenedores en función de la carga de trabajo, lo que hace que las aplicaciones sean altamente escalables y rentables en la nube.
### Arquitectura de soluciones
- ##### Monolítico:
	- Toda la aplicación se desarrolla y despliega como una única unidad. Esto significa que todos los componentes de la aplicación (frontend, backend, bases de datos, etc.) se agrupan en una sola aplicación monolítica.
	- Se escala clonando la aplicación en múltiples servidores/VM
- ##### Microservicios:
	- Una aplicación de microservicio segrega la funcionalidad en servicios más pequeños separados.
	- Se escala implementando cada uno servicio independiente con múltiples instancias a lo largo servidores/VM
	- En una implementación basada en microservicios, la aplicación se divide en componentes más pequeños e independientes llamados microservicios. Cada microservicio se centra en una tarea específica o una parte de la funcionalidad de la aplicación.
	- ###### Uso de API Gateway Service
		- ![[Pasted image 20230920193253.png]]
		- Actúa como un proxy inverso, enrutando solicitudes de clientes a servicios. También puede realizar diversas tareas transversales, como autenticación, terminación SSL y limitación de velocidad.
		- El API Gateway puede gestionar la tasa de solicitudes, limitar el acceso a recursos para evitar la sobrecarga de servicios backend y proporcionar un control más granular sobre el tráfico.
	- Uso de API Gateway con Azure API Managment
		- ![[Pasted image 20230920193455.png]]
		- Es una práctica y conjunto de herramientas que se utiliza para supervisar, gestionar y proteger las APIs
		- El API Management permite supervisar y analizar el tráfico de las APIs. Esto incluye el seguimiento del uso de las APIs, la identificación de problemas de rendimiento y la generación de informes para evaluar el rendimiento y la eficiencia de las APIs.
		- Proporciona mecanismos para garantizar la seguridad de las APIs.
		- Proporciona un portal de desarrolladores donde los creadores de aplicaciones pueden acceder a la documentación, obtener claves de API y probar las APIs. Esto facilita la colaboración con desarrolladores externos y la adopción de las APIs.
		- Permite a las organizaciones rastrear el uso de las APIs y facturar a los clientes según su consumo.
- ##### Terraform
	- ![[Pasted image 20230920194422.png]]
	- Terraform es una herramienta de código abierto desarrollada por HashiCorp que se utiliza para la automatización y gestión de la infraestructura como código (IaC, por sus siglas en inglés). Terraform permite a los equipos de operaciones y desarrolladores definir y provisionar recursos de infraestructura de manera declarativa, lo que significa que describen la infraestructura deseada y Terraform se encarga de crear, modificar y eliminar los recursos de acuerdo con esa descripción.
	- Terraform permite definir la infraestructura como código en archivos de configuración. Estos archivos describen los recursos de infraestructura necesarios, como máquinas virtuales, redes, bases de datos, almacenamiento y más.
	- En lugar de especificar los pasos detallados para crear recursos, los archivos de configuración de Terraform declaran el estado deseado de la infraestructura. Terraform se encarga de determinar cómo llevar la infraestructura desde su estado actual hasta el estado deseado.
	- Terraform es compatible con una amplia variedad de proveedores
- Referencias:
	- **[https://learn.microsoft.com/es-es/training/paths/create-microservices-with-dotnet/](https://learn.microsoft.com/es-es/training/paths/create-microservices-with-dotnet/)**
	- **[https://learn.microsoft.com/es-mx/training/paths/microsoft-azure-fundamentals-describe-cloud-concepts/](https://learn.microsoft.com/es-mx/training/paths/microsoft-azure-fundamentals-describe-cloud-concepts/)**
	- **[https://learn.microsoft.com/es-es/training/paths/azure-fundamentals-describe-azure-architecture-services/](https://learn.microsoft.com/es-es/training/paths/azure-fundamentals-describe-azure-architecture-services/)**
- **¿De qué forma puedo conectar una nube a un datacenter on-premise?**
	- **Site-to-Site VPN:** Esta es una opción común para conectar nubes públicas como AWS, Azure o Google Cloud con tu datacenter local. Un túnel VPN se establece entre el gateway VPN en tu datacenter y el gateway VPN proporcionado por el proveedor de la nube. Esto permite que los recursos en ambas ubicaciones se comuniquen de manera segura como si estuvieran en la misma red local.
	- **Direct Connect (AWS) o ExpressRoute (Azure)** :Estos son servicios de conectividad proporcionados por AWS y Azure, respectivamente, que permiten conexiones dedicadas y de alta velocidad entre tu datacenter y la nube. Esto es particularmente útil para aplicaciones que requieren un alto ancho de banda y baja latencia.
	- **Gateway de VPN de Cloud (Cloud VPN Gateway):** Algunos proveedores de nube ofrecen servicios de gateway de VPN en la nube que actúan como punto de entrada para conectar tu red local con la nube. Esto puede ser útil si deseas centralizar la gestión de la conexión en la nube.
- **¿Para qué me sirve la Infraestructura como Código?**
	- IaC permite automatizar la creación, configuración y despliegue de recursos de infraestructura, como servidores, redes, bases de datos y servicios en la nube. Esto simplifica y acelera el proceso de implementación, reduciendo errores humanos y aumentando la coherencia de la infraestructura.
	 - Puedes describir toda tu infraestructura en código, lo que facilita la reproducción exacta de entornos en diferentes ubicaciones o momentos en el tiempo. Esto es útil para entornos de desarrollo, pruebas y producción consistentes.