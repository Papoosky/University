![[Pasted image 20230912115213.png]]

- #### ¿Qué es una interacción?
	- Un patrón de intercambios de mensajes que se realizan para lograr un propósito específico es lo que se denomina una interacción.

## Diagrama de interacción
- Es un conjunto de objetos y sus relaciones, incluyendo los mensajes que se pueden enviar entre ellos
- En si muestran cómo se comunican los objetos.
- #### Vista de interacción
	- La vista de interacción proporciona una vista completa del comportamiento del sistema, es decir, muestra el flujo de control a través de muchos objetos.
- #### Aspectos comunes de la interacción
	- Objetos: Son los que participan en la interacción
	- Roles: Son las acciones de los objetos 
	- Enlaces: Es la conexión entre objetos
	- Mensajes: Es la comunicación entre objetos
	- Secuenciación: Es el orden de los mensajes
- #### Características
	- Son técnicas gráficas.
	- Son modelos que se describen como grupo de objetos.
	- Estos diagramas muestran objetos, así como los mensajes que se pasan entre ellos.
- #### Objetivo
	- Sirve para la representación precisa de las interacciones entre objetos.
	- Verificar la coherencia del sistema.
	- Su misión es localizar el comportamiento de los objetos
- #### Utilidad
	- Los diagramas de interacción se utilizan para modelar los aspectos dinámicos de un sistema, lo que conlleva modelar instancias concretas.
- #### Ventajas
	- Son dinámicos.
	- Se sabe el tiempo de vida de un determinado objeto
	- Representan objetos y mensajes de objetos.
	- Son isomórficos.
- #### Clasificación
	- Diagrama de secuencia
	- Diagrama de colaboración

### Diagrama de secuencia
- Un diagrama de secuencia es un diagrama de interacción que resalta la ordenación temporal de los mensajes. Un diagrama de secuencia presenta un conjunto de objetos y los mensajes enviados y recibidos por ellos. Los diagramas de secuencia ponen especial énfasis en el orden y el momento en que se envían los mensajes a los objetos.
- #### Objetivo 
	- Su finalidad es describir los mensajes que intercambian los distintos objetos para cumplir con las responsabilidades definidas en un escenario concreto de un Caso de Uso.
- #### Características
	- Se muestra el flujo de control de los mensajes.
	- Cada objeto viene mostrado por una barra vertical que es la que da idea del tiempo.
	- La línea vertical representa el paso del tiempo (de arriba hacia abajo).
	- Se muestran los objetos que interactúan.
	- Se muestra el tiempo de vida de un objeto.
	- Los diagramas de secuencia tienen dos aspectos que los <mark style="background: #FF5582A6;">distinguen de las características de los diagramas de colaboración:</mark>
		1. La Línea de Vida, que representa la existencia de un objeto a lo largo de un período de tiempo.
		2. El Foco de Control, representa el período de tiempo durante el cual un objeto ejecuta una acción.
- #### Ventajas
	- Enfatiza el tiempo que indica el orden de los mensajes.
	- Es útil para describir escenarios donde existe interacción con el usuario.
- #### Desventajas
	- El tiempo que se le da a cada mensaje no es el mismo al tiempo real de ejecución.
	- No muestra las relaciones que hay entre los objetos
- #### Elementos
	- En un diagrama de secuencia existen en consecuencia 3 tipos de elementos
		- Objetos
			- ![[Pasted image 20230912120932.png]]
		- Foco de Control
			- ![[Pasted image 20230912120947.png]]
		- Tipos de Mensajes
			- ![[Pasted image 20230912120957.png]]
			- Síncrono o Llamada : El originario del mensaje pierde el control hasta recibir la respuesta. 
				- ![[Pasted image 20230912121019.png]]
			- Asincrónico: El originario no espera respuesta permanece activo pudiendo enviar mensajes
				- ![[Pasted image 20230912121030.png]]
			- Retorno o Returns:No es un mensaje, sino la respuesta de un mensaje previo.
				- ![[Pasted image 20230912121054.png]]
			- Directo o Flat: El originario no espera respuesta, pero se pasa el control al que recibe el mensaje, el fin del foco de control devuelve el control.
				- ![[Pasted image 20230912121119.png]]
![[Pasted image 20230912121245.png]]

- ## Ejemplo 1
	- Se trata de un juego de ajedrez que va a contener: 
	- El actor (persona que efectúa el evento) 
	- Los objetos: 
		- Usuario 
		- Tyr (tablero y reglas) 
		- Ag (algoritmo)
	![[Pasted image 20230912121327.png]]
- ## Ejemplo 2
	- Este ejemplo se basa en la atención en un restaurante, donde existen 4 objetos que interactúan.
	- ![[Pasted image 20230912121354.png]]
## Diagrama de colaboración
- Un diagrama de colaboración es una descripción de una colección de objetos que interactúan para implementar un cierto comportamiento dentro de un contexto. Describe una sociedad de objetos cooperantes unidos para realizar un cierto propósito.
- ![[Pasted image 20230912140030.png]]
- #### Objetivos
	- Destaca la organización de los objetos que participan en una interacción.
	- Dar una visualización clara del flujo de control en el contexto de la organización estructural de los objetos que colaboran.
	- Enfatizar la organización estructural de los objetos que envían y reciben mensajes.
- #### Ventajas
	- Son útiles en la fase exploratoria para identificar objetos.
	- La distribución de los objetos en el diagrama permite observar adecuadamente la interacción de un objeto con respecto de los demás.
- #### Elementos
	- Objetos
		- ![[Pasted image 20230912140208.png]]
	- Mensajes
		- ![[Pasted image 20230912140216.png]]
	- Vínculos
### Ejemplo 
- ![[Pasted image 20230912140303.png]]