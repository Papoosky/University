![](https://lh5.googleusercontent.com/qXHAbDCEGci6w8_q-XqlHO0l3WmjVHS45zMWa_KudMn3Kgn_3dECMRgblGsLcN8HOl72K5GvZgSkKlMwpUY0sV4f8QAgJxU_5GSTOLO1yZePz3rSmG3pOVmC_Su2HXDNNOTMaRoQtOTFX-QJnNjI6cg52Q=s2048)

### Software as a service 
- Permite a los usuarios conectarse a aplicaciones basadas en la nube a través de internet y usarlas. 
- El proveedor de servicios proporciona y gestiona toda la pila de aplicaciones a través de Internet, desde la infraestructura de hardware hasta la propia aplicación. El proveedor se encarga de gestionar todas las actualizaciones, corregir errores y otros pasos de mantenimiento generales. Solo tienes que conectarte a la aplicación.

   El proveedor administra hardware y software
	- Ejemplos: Correo electrónico, calendarios, herramientas como Office 365
- Ventajas: 
	- Obtén acceso a aplicaciones sofisticadas
	- Paga solo por lo que uses
	- Usa software cliente gratuito
	- Moviliza a tus recursos fácilmente
	- Accede a los datos de las aplicaciones desde cualquier lugar

### Function as a service

- La función como servicio (FaaS) es un tipo de servicio de cloud computing que permite a los desarrolladores diseñar, ejecutar y gestionar paquetes de aplicaciones como funciones sin tener que preocuparse por el mantenimiento de su propia infraestructura
- Típicamente usado para construir microservicios
- FaaS te permite compilar e implementar un pequeño fragmento de código, o una función, que realiza una tarea específica. El proveedor de servicios en la nube agrega escalamiento si es necesario cuando se ejecuta una función

### Platform as a service

- El proveedor de servicios proporciona y gestiona todos los recursos de hardware y software necesarios para el desarrollo de aplicaciones. Tú escribes el código y gestionas todas las aplicaciones y datos, pero no tienes que gestionar la plataforma de desarrollo de software ni mantenerla.
- Ejemplo: google app engine, google cloud run 
- Ventajas: 
	- Tiempo de lanzamiento más rápido
	- Escalabilidad fácil: PaaS te permiten reducir verticalmente en periodos de poco tráfico o escalar verticalmente para hacer frente a los aumentos inesperados en la demanda.
	- Seguridad compartida: Con la plataforma como servicio, el proveedor se encarga de proteger la infraestructura.
	- Acceso flexible: Los equipos de desarrollo y DevOps pueden acceder a herramientas y servicios de PaaS compartidos desde cualquier lugar y en cualquier dispositivo a través de una conexión a Internet.

### Container as a service 

- Esencialmente alojamiento e implementación automatizados de paquetes de software en contenedores
- Los tiempos de ejecución de contenedores ofrecen configuración y virtualización del sistema operativo, lo que permite una personalización y control avanzados. Los contenedores pueden ser fundamentales para el desarrollo de software altamente personalizado y especializado. Sin embargo, para software más genérico y estándar, PaaS suele ser la mejor opción.
- CaaS puede ser una mejor opción para los microservicios , ya que cada contenedor implementado en CaaS puede tener su propio sistema operativo y pila de lenguaje encapsulados.

### Infraestructure as a service

- Es un modelo de servicio en la nube que ofrece recursos de infraestructura bajo demanda, como computación, almacenamiento, redes y virtualización, a empresas y particulares a través de la nube.
- Este es el método más rápido y económico de migrar una aplicación o carga de trabajo a la nube. Sin refactorizar su arquitectura subyacente, puede aumentar la escala y el rendimiento, mejorar la seguridad y reducir los costos de ejecución de una aplicación o carga de trabajo.

### Traditional on premises

- Tú manejas hasta el hardware utilizado, generalmente data centers propios de la empresa o alquilados

- **¿Qué diferencia hay entre CaaS y FaaS?**
	- CaaS se centra en el despliegue de aplicaciones en contenedores, que son unidades de implementación más grandes y completas. Los contenedores pueden incluir múltiples componentes y servicios.
	- Con CaaS, los usuarios son responsables de gestionar y configurar la infraestructura subyacente, como servidores virtuales o físicos, y orquestar los contenedores utilizando herramientas como Docker Swarm o Kubernetes.
	- FaaS se centra en implementar funciones individuales (también conocidas como "serverless functions" o "funciones sin servidor"). Estas funciones son unidades de código pequeñas y específicas que se ejecutan en respuesta a eventos.
	- En FaaS, la infraestructura subyacente se gestiona completamente de forma automática por el proveedor de servicios en la nube. Los desarrolladores no necesitan preocuparse por la administración de servidores ni la orquestación.