### Sistema Operativo

- Definición: Es un software que abstrae y controla los recursos de hardware de un computador, tiene 3 tareas **fundamentales**:
	- Esconder la complejidad del hardware
	- Manejo de recursos 
	- Proveer de aislamiento y protección 
- Elementos
	- Abstracciones:
		- Hardware: Memoria, archivo, sockets, ...
		- Procesos, threads
	- Mecanismos: 
		- Cómo crear, ejecutar un proceso
		- Cómo reservar memoria
	 - Políticas:
		 - Tamaño de memoria que un proceso puede solicitar 
		 - Número de sockets que un proceso puede abrir
		 - Qué espacio de memoria liberar primero 
- Manejo de memoria
	- Abstracción:
		- Memory page (Bloque contiguo de memoria virtual)
	 - Mecanismos:
		 - Reservar, asignar a un proceso 
	 - Política: 
		 - Least Recently Use (LRU) (Estrategia de almacenamiento en caché)(https://www.topcoder.com/thrive/articles/lru-cache#:~:text=Least%20Recently%20Used%20(LRU)%20is,be%20asked%20with%20some%20variation.)

### ¿Cómo diseñar un sistema operativo?

- Principios 
	1. Separar mecanismos de políticas
		- Mecanismos flexibles para soportar muchas políticas
		- Memoria: Mecanismos -> procesos; Políticas -> manejo(LRU, LFU, random)
	 2. Optimizar para el caso más común 
		 - ¿Para qué se va a usar? ¿Quién lo va a usar? 
		 - Elegir políticas que tengan sentido dadas estas preguntas
		 - Excepciones ocurren pero NO son relevantes
 - Protección por aislamiento 
	 - User level
		 - Unprivileged
	 - Kernel level 
		 - Privileged 
	  Switch entre estos dos modos es dado por el hardware

*Meltdown* : Vulnerabilidad en arquitecturas intel, rompe el mecanismo que impide que las aplicaciones accedan a la memoria del sistema

### System calls 

![[Pasted image 20230831123254.png]]

- Asociadas con un código que define que operación llamar, de donde obtener los argumentos y el valor de ellos 
![[Pasted image 20230831123540.png]]

- Sincrónicas
	- Existen mecanismos (señales) para hacerlo asíncronas, pero es más complejo 
 - Operaciones caras
	 - Toma tiempo hacer un cambio de contexto 
	 - Afecta al cache

### Tipos de SOs 
- Monolítico: Todos los servicios o drivers de hardware están incluidos en el sistema operativo
	- Optimiza procesos
	- Difícil de mantener 
	- Muy pesados 
- Modular: Todos los servicios se pueden agregar como módulo 
	- Define una interfaz
	- Se cargan según necesidad
	- Puede impactar el rendimiento
- Micro Kernel: Tiene lo básico de un sistema operativo, otros componentes son aplicaciones
	- Muy pequeño (seguro)
	- Muchas interacciones entre procesos
	- Costoso en términos de rendimiento