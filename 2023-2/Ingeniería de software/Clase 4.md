# UML

- Es un lenguaje de modelamiento para la especificación, visualización, construcción y documentación de los artefactos. UML ayuda a mostrar errores potenciales en las estructuras de aplicaciones, el comportamiento del sistema y otros procesos empresariales.

- ### Ventajas de usar UML
	- Simplifica las complejidades 
	- Mantiene abiertas las líneas de comunicación
	- Automatiza la producción de software y los procesos 
	- Ayuda a resolver los problemas arquitectónicos constantes
	- Aumenta la calidad del trabajo 
	- Reduce loa costos y el tiempo de comercialización

- ### Diagramas de casos de uso
	- Es un diagrama de conocimiento
	- Sirve para representar los actores externos que interactúan con el sistema de información y a través de qué funcionalidades (casos de uso o requisitos funcionales) se relacionan
	- Representar los requisitos funcionales
	- Representar los actores que se comunican con el sistema. Normalmente los actores del sistema son los usuarios y otros sistemas externos que se relacionan con el sistema. En el caso de los usuarios hay que entender el actor como un “perfil”, pudiendo existir varios usuarios que actúan como el mismo actor. Ejemplo: Administrador, paciente, cliente, bodegero, etc.
	- Representar las relaciones entre requisitos funcionales y actores.
	- Guiar el desarrollo del sistema. Crear un punto de partida sobre el que empezar a desarrollar el sistema.
	- Comunicarse de forma precisa entre cliente y desarrollador. Simplifica la forma en que todos los involucrados en el desarrollo, incluyendo el cliente, perciben como el sistema funcionará y ofrecerá una visión general común del mismo.

	- ### Actores
		- Es algo o alguien externo al sistema que interactúa de forma directa con el sistema.
		- Con interactuar nos referimos a que aporta información, recibe información, inicia una acción...
		- ![[Pasted image 20230912111833.png]]
	- ### Casos de uso
		- Un caso de uso se utiliza para representar una de las funcionalidades que realiza el sistema. Es una secuencia de acciones que hace el sistema y que producen un resultado que puede percibir un usuario.
		- ![[Pasted image 20230912112002.png]]
	- ### Relaciones
		- Las relaciones conectan los casos de uso con los actores o los casos de uso entre sí
		- ![[Pasted image 20230912112319.png]]
		- #### Tipos de relaciones 
			- <<'include'>>: 
				- Se utiliza para representar que un caso de uso utiliza siempre a otro caso de uso. Es decir, un caso de uso se ejecutará obligatoriamente (lo incluye, lo usa). Se representa con una flecha discontinua que va desde el caso de uso de origen al caso de uso que se incluye.
				- ![[Pasted image 20230912112548.png]]
				- Un uso típico de este tipo de relaciones se produce cuando dos casos de uso comparten una funcionalidad. Esa funcionalidad es extraída de los dos y se crea un caso de uso nuevo que se relaciona con los anteriores con un <'include'>.
				- ![[Pasted image 20230912112634.png]]
			- <<'extend'>>:
				- Este tipo de relaciones se utilizan cuando un caso de uso tiene un comportamiento opcional, reflejado en otro caso de uso. Es decir, un caso de uso puede ejecutar, normalmente dependiendo de alguna condición o flujo del programa, otro caso de uso. Se representa con una flecha discontinua que va desde el caso de uso opcional al original.
				- ![[Pasted image 20230912112748.png]]
				- En este supuesto el caso de uso Hacer pedido puede dar lugar (o no) a otros dos casos de uso: Notificar por mensaje y notificar por correo. Se supone que, cuando un usuario hace un pedido, el sistema le permite elegir si quiere que se envíe una notificación de ese pedido por mensaje o por correo.
				- ![[Pasted image 20230912112821.png]]
			- Generalización:
				- Consiste en hacer que un elemento herede el comportamiento de otro. Aunque se puede utilizar entre casos de uso, es más común utilizarlo entre actores, haciendo que uno de los actores tengan acceso a las funcionalidades de otro. Se representa con una flecha con la punta hueca que va desde el elemento que hereda al elemento heredado
				- ![[Pasted image 20230912113114.png]]
		![[Pasted image 20230912113433.png]]