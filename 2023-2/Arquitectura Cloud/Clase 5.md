
## Arquitectura IaaS

![[Pasted image 20230922155028.png]]

### Forma de identificar
- Las maquinas virtuales son un rasgo característicos de la infraestructura como servicio
- Una IaaS generalmente incluirá redes virtuales y subredes que conecten las VMs
- Load balancer es común para distribuir el tráfico entre las VMs
- Almacenamiento en la nube

### Servicios

- #### Front Door:
	- Azure Front Door es un servicio de enrutamiento de tráfico global y un equilibrador de carga que se utiliza para optimizar la distribución de tráfico web a través de múltiples regiones geográficas. Funciona como una puerta de entrada a tus aplicaciones y permite enrutar el tráfico de manera eficiente a la región de Azure más cercana al usuario final.
	- Mejora la velocidad de entrega del contenido a los usuarios finales al enrutarlos a la región más cercana.
	- Proporciona análisis y supervisión del tráfico web.

- #### Azure Web Application Firewall (WAF):
	- Es un servicio de seguridad que protege las aplicaciones web contra amenazas y ataques cibernéticos comunes, como ataques de inyección SQL, ataques de denegación de servicio distribuido (DDoS) y más.
	- Filtra el tráfico web y bloquea automáticamente las amenazas conocidas antes de que lleguen a tu aplicación.
- #### Internal Load Balancer:
	- Servicio que distribuye el tráfico de red (TCP/UDP) entre múltiples recursos informáticos (como máquinas virtuales o instancias de servidores) dentro de la misma red virtual de Azure.
- #### Subnet:
	- Una subred es una división lógica de una red virtual en la nube. Permite segmentar una red virtual en múltiples segmentos más pequeños, lo que facilita la organización y la gestión de los recursos y la seguridad de la red.
- #### Network Security Group (NSG):
	- Componente de seguridad que se utiliza para controlar el tráfico de red entrante y saliente hacia y desde los recursos de una subred. Un NSG contiene reglas de seguridad que especifican qué tipos de tráfico se permiten o bloquean. Puedes pensar en un NSG como un firewall de red que se aplica a nivel de red virtual o subred.
- #### Azure NetApp Files:
	- Servicio de almacenamiento gestionado proporcionado por Microsoft Azure que ofrece almacenamiento de archivos empresariales de alto rendimiento y escalable.
- #### Azure Cache for Redis:
	- Azure Cache for Redis almacena datos en memoria para proporcionar acceso rápido y de baja latencia a datos comúnmente utilizados, lo que mejora el rendimiento de las aplicaciones.
- #### Azure Key Vault:
	- Servicio gestionado de Microsoft Azure que se utiliza para proteger, gestionar y controlar el acceso a secretos, claves de cifrado y certificados utilizados en aplicaciones y servicios en la nube. Azure Key Vault proporciona una forma segura de almacenar y administrar información confidencial y cifrada, lo que es fundamental para garantizar la seguridad de los datos en una variedad de escenarios.
- #### Private Endpoint:
	- Componente de red en la nube que permite que los recursos y servicios en una red virtual de la nube se conecten de manera segura y privada a un servicio de nube específico, como una base de datos, un servicio de almacenamiento o cualquier otro servicio que admita conexiones mediante puntos de conexión privados. Estos puntos de conexión privados se utilizan para garantizar que la comunicación entre los recursos de la red virtual y el servicio de la nube se realice a través de la infraestructura de red de la nube de manera privada y sin pasar por la internet pública.

-------------------------- ####### ------------------------------
## Arquitectura PaaS

![[Pasted image 20230922164953.png]]
### Forma de identificar
- No se verán representaciones de máquinas virtuales (la infraestructura subyacente está completamente gestionada por el proveedor de la plataforma.)
- Es posible que veas elementos que representan una plataforma de desarrollo o servicios de aplicaciones, como "Azure App Service" o "Google App Engine.", "Firebase", "Azure Functions"
### Servicios
- #### Azure Blob Storage (símil cloud storage)
	- Está diseñado para almacenar y administrar grandes cantidades de datos no estructurados, como imágenes, videos, documentos, archivos de registro y otros tipos de archivos binarios o de texto. Azure Blob Storage es parte de la oferta de almacenamiento de objetos de Azure. 
- #### Azure App Service Plan
	- Proporciona una infraestructura para alojar aplicaciones web, API y servicios en la nube. Permite a los desarrolladores enfocarse en el desarrollo de aplicaciones sin preocuparse por la infraestructura subyacente.
	- Define el nivel de recursos y el tamaño de las máquinas virtuales que se utilizarán para hospedar tus aplicaciones web.
	- Puedes configurar una o varias instancias. Las instancias son máquinas virtuales individuales que se utilizan para alojar y ejecutar tus aplicaciones web. Puedes ajustar la cantidad de instancias según la demanda de tráfico y la escalabilidad que necesitas para tu aplicación.
- #### Service Endpoint
	- Es una característica en la nube que permite conectar de manera segura los recursos de una red virtual a un servicio específico en la nube, como Azure SQL Database, Azure Storage, Azure Cosmos DB u otros servicios administrados. Los Service Endpoints permiten que estos recursos de la red virtual accedan a los servicios de la nube a través de una conexión privada en lugar de atravesar la Internet pública, lo que mejora la seguridad y el rendimiento de las comunicaciones.
- #### Azure Private DNS Zone
	- Permite a las organizaciones crear su propia infraestructura de resolución DNS interna sin depender de servicios DNS públicos. Esto es particularmente valioso en escenarios de redes virtuales aisladas o híbridas donde se necesitan nombres de dominio privados y resolución DNS segura.

## Arquitectura PaaS

![[Pasted image 20230922172335.png]]
### Forma de identificar
- AKS se considera un servicio administrado de Kubernetes, lo que lo coloca en un punto intermedio entre IaaS (Infraestructura como Servicio) y PaaS.
- Se puede considerar una solución de contenedor como servicio (CaaS)
### Servicios

- #### Ingress
	- Es un recurso que administra las reglas de enrutamiento del tráfico HTTP y HTTPS desde el exterior del clúster de Kubernetes hacia los servicios dentro del clúster.
- #### Secret store CSI
	- Esta tecnología permite que las aplicaciones y los contenedores accedan a secretos, como contraseñas, tokens de autenticación u otros datos confidenciales, sin tener que almacenarlos directamente en las imágenes de contenedor o en configuraciones de texto claro.
- #### Azure Container Registry
	- Permite a los desarrolladores y equipos de operaciones almacenar imágenes de contenedor Docker en un repositorio centralizado basado en la nube.
	- Herramientas y funcionalidades para administrar imágenes de contenedor, incluyendo la capacidad de etiquetar versiones, organizar imágenes en repositorios y realizar operaciones de limpieza y eliminación.

## ¿Qué desventajas existen en el uso de servicios en la nube?
Lock in, dependencia con el proveedor