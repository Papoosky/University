### Metodologías - Problemas

- ¿Cómo modelar el sistema real para entenderlo?
- Cómo abstraerlo y llevarlo a una representación adecuada al diseño y construcción de un software?

--- Análisis y Diseño Orientado al Objeto (usando UML)

- Herramientas en el análisis
 ![[Pasted image 20230904162449.png]]
- Etapas en el análisis:
	- Describir las acciones de los usuarios en el dominio del problema
	- Describir los objetos del dominio del problema
	- Describir la secuencia de actividades del sistema

--------- Ejemplo juego de dados:  -------
- Tenemos dos dados
- Lanzamos los dados 
- Si obtenemos entre 2 y 8 puntos, perdemos 
- Si obtenemos más de 8 puntos, ganamos

- AOO juego de dados: **Casos de uso** (acciones)

	- ![[Pasted image 20230904163254.png]]


- AOO Juego de dados: **Modelo de dominio** (entidades)

	- ![[Pasted image 20230904163343.png]]

- AOO Juego de dados: **Diagrama de interacción** (interacción de entidades)


	- ![[Pasted image 20230904163433.png]]

- AOO  Juego de dados: **Diagrama de actividades** (secuencia de decisiones)
	- Tiene que ver con modelar procesos de sistemas
	- También se usa para modelar softwares complejos
		![[Pasted image 20230904163729.png]]

- Resumen y ejercicio de AOO Y DOO
	- ![[Pasted image 20230904164106.png]]
	-  DOO Juego de dados: Diagrama de clases
		- ![[Pasted image 20230904164158.png]]
	- DOO Juego de dados: Diagrama de interacción
		- ![[Pasted image 20230904164234.png]]
- Relaciones entre artefactos UML
![[Pasted image 20230904213202.png]]
- Los casos de uso proveen los nombres para las descripciones
- Los casos de uso se emplean para crear los diagramas de interacción del sistema
![[Pasted image 20230904213315.png]]
- Los nombres de conceptos del dominio inspiran la descripción de los casos de uso
![[Pasted image 20230904213406.png]]
- Clases descubiertas mientras se crean los diagramas de interacción
![[Pasted image 20230904213437.png]]
