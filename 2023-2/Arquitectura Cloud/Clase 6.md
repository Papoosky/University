![[Pasted image 20230922200837.png]]

## Organización de google cloud

![[cloud-hierarchy.svg]]

- ### Organización
	-  Representa una organización (por ejemplo, una empresa) y es el nodo raíz en la jerarquía de recursos de Google Cloud cuando está presente
- ### Carpeta
	- Proporcionan un mecanismo de agrupación adicional y límites de aislamiento entre proyectos.
	- Los recursos de carpetas se pueden usar para modelar diferentes entidades, departamentos y equipos legales dentro de una empresa.
- ### Proyectos
	- El recurso de proyecto es la entidad organizadora básica. Los recursos de organización y carpeta pueden contener varios proyectos. Se requiere un recurso de proyecto a fin de usar Google Cloud, y forma la base para crear, habilitar y usar todos los servicios de Google Cloud, administrar API, habilitar la facturación, agregar y quitar colaboradores y administrar permisos.
- ## Herencia de políticas de IAM
	-  Los recursos heredan las políticas del recurso superior. Si configuras una política a nivel de la organización, la heredarán todos sus recursos de carpeta y proyecto secundarios. Si estableces una política a nivel de proyecto, la heredarán todos sus recursos secundarios.
## Organización de AWS

![[Pasted image 20230922211533.png]]

- ### Organización
	- Una entidad que crea para consolidar sus cuentas de AWS para que pueda administrarlas como una sola unidad. Puede organizar las cuentas en una estructura jerárquica en forma de árbol con una raíz en la parte superior y unidades organizativas anidadas debajo de la raíz. Cada cuenta puede estar directamente en la raíz o ubicarse en una de las unidades organizativas de la jerarquía. Una organización tiene la funcionalidad determinada por el conjunto de características que usted habilita.

- ### Raíz
	- El contenedor principal de todas las cuentas de su organización. Si aplica una política a la raíz, se aplica a todas las unidades organizativas (OU) y cuentas de la organización.

- ### Unidad organizativa (OU)
	- Un contenedor para cuentas dentro de una raíz . Una unidad organizativa también puede contener otras unidades organizativas, lo que le permite crear una jerarquía que se asemeja a un árbol al revés, con una raíz en la parte superior y ramas de unidades organizativas que llegan hacia abajo y terminan en cuentas que son las hojas del árbol. Cuando adjunta una política a uno de los nodos de la jerarquía, fluye hacia abajo y afecta a todas las ramas (OU) y hojas (cuentas) debajo de ella. Una unidad organizativa puede tener exactamente una unidad organizativa principal y, actualmente, cada cuenta puede ser miembro de exactamente una unidad organizativa.

- ### Cuenta
	- Una cuenta en Organizaciones es una cuenta de AWS estándar que contiene sus recursos de AWS y las identidades que pueden acceder a esos recursos.

## Organización de Azure

![[Pasted image 20230922211854.png]]

- ### **Los grupos de administración** 
	- Ayudan a administrar el acceso, las políticas y el cumplimiento de múltiples suscripciones. Todas las suscripciones de un grupo de administración heredan automáticamente las condiciones que se aplican al grupo de administración.
    
- ### **Las suscripciones** 
	- Asocian lógicamente cuentas de usuario con los recursos que crean. Cada suscripción tiene límites o cuotas sobre la cantidad de recursos que puede crear y utilizar. Las organizaciones pueden utilizar suscripciones para gestionar los costos y los recursos creados por usuarios, equipos y proyectos.
    
- ### **Los grupos de recursos**
	- Son contenedores lógicos donde puede implementar y administrar recursos de Azure, como aplicaciones web, bases de datos y cuentas de almacenamiento.
    
- ### **Los recursos**
	- Son instancias de servicios que puede crear, como máquinas virtuales, almacenamiento y bases de datos SQL.

## Organización de redes Google Cloud

![[vpc-overview-example.svg]]

- En Google Cloud, las redes virtuales se denominan "VPC" (Virtual Private Cloud). Dentro de una VPC, puedes crear subredes, y estas subredes pueden estar asociadas a una o más regiones geográficas de Google Cloud. Esto significa que puedes tener subredes que abarquen múltiples zonas dentro de una región. Además, puedes tener una zona que pertenezca a más de una subred.
## Organización de redes AWS

![[how-it-works.png]]

- En AWS, las redes virtuales se llaman "VPC" al igual que en Google Cloud. Dentro de una VPC de AWS, puedes crear subredes, pero estas subredes están asociadas a una única zona de disponibilidad (AZ) específica. En AWS, una zona de disponibilidad es un datacenter físico o un grupo de datacenters. Por lo tanto, si deseas tener subredes en múltiples zonas de disponibilidad, deberás crear subredes separadas en cada una de ellas.
## Organización de redes Azure
![[Pasted image 20230922213242.png]]

En Azure, las redes virtuales se denominan "VNET" (Virtual Network). Al igual que en AWS, las subredes en Azure están asociadas a una única región. Puedes distribuir máquinas virtuales en conjuntos de disponibilidad para lograr la alta disponibilidad, pero esto se gestiona de manera diferente a cómo se gestionan las subredes.