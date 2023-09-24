# Métricas
- Las métricas son aquellos datos expresados numéricamente que nos sirven para analizar el rendimiento de un determinado proceso.
- Nosotros lo usaremos para comparar las distintas <mark style="background: #FF5582A6;">políticas de programación de procesos</mark>.

## Turnaround Time
- <mark style="background: #FF5582A6;">Es una métrica para medir rendimiento</mark> 
- Se define como el tiempo en que se completa un proceso menos el tiempo en que arribó el proceso al sistema
- ![[Pasted image 20230918131710.png]]
### Primera política: **First-In First-Out**
- FIFO: el primer proceso que entra es el primero que se ejecuta
	- Ejemplo 1
		- Supongamos que tenemos tres procesos: PA, PB y PC. Asumamos que: 
			- Los procesos tienen un mismo largo (10 secs) 
			- Los procesos llegan al mismo tiempo (podemos asumir Tarrival = 0) 
			- No hay I/O ni interrupciones de timeout
		- ¿Cúal es el turnaraound time promedio?
			- ![[Pasted image 20230918132228.png]]
	- Ejemplo 1 - v2
		- Supongamos que todos llegan al mismo tiempo, pero se asigna primero el proceso A con un tiempo de 40 segundos
			- ![[Pasted image 20230918132833.png]]
### Segunda política: **Shortest Job First**
- SJF: el proceso más corto es el primero que se ejecuta
	- Ejemplo 1 - v3 
		- ![[Pasted image 20230918133317.png]]
- SJF es óptimo si todos los procesos arriban al mismo tiempo, pero eso no es lo que sucede en los computadores modernos.
	- Ejemplo 1 - v4
		- Supongamos que A llega en el tiempo 0 y los demás en el tiempo 10
			- ![[Pasted image 20230918133455.png]]
### Tercera política: **Shortest Time to Completion First**
- STCF: el proceso que vaya a terminar antes se ejecuta, indiferente al tiempo de llegada
	- Ejemplo 1 - v4
		- Supongamos que A llega en el tiempo 0 y los demás en el tiempo 10
			- ![[Pasted image 20230918133950.png]]
			- STCF es óptimo si sabemos los tiempos de ejecución de los procesos y no hay I/O Pero, ¿es válido hoy?

#### Batch vs Time Shared
- Los computadores antiguos funcionaban de manera <mark style="background: #FF5582A6;">batch</mark>, es decir, un proceso a la vez en la CPU Sin embargo hoy queremos emular la ejecución de múltiples procesos en paralelo, es decir, <mark style="background: #FF5582A6;">time shared</mark> 

## Response Time
- Se define como el tiempo en que se ejecuta por primera vez un proceso menos el tiempo en que arribó el proceso al sistema
- ![[Pasted image 20230918134226.png]]
- Esta es otra métrica para <mark style="background: #FF5582A6;">medir justicia</mark> 

- Ejemplo 1 - v6
	- ![[Pasted image 20230918134338.png]]
- Ejemplo 1 -v7 
	- ![[Pasted image 20230918134422.png]]
### Cuarta política: **Round Robin**
- RR o Time slicing divide los procesos en períodos de tiempos (time slice o scheduling quantum) y ejecuta “poco a poco” cada proceso Los períodos de tiempo pueden ser cualquier múltiplo de el timer interrupt
- Ejemplo 1 - v8
	- ![[Pasted image 20230918191421.png]]
- RR tiene el problema de determinar cuál time slice es el óptimo de forma de tener buen response time, pero no hacer el sistema inestable por demasiados cambios de contexto → Amortización
- ![[Pasted image 20230918191554.png]]
#### Rendimiento vs justicia
- Round Robin tiene un mal turnaround time, pero es el que posee mejor response time. 
- STCF es óptimo para turnaorund, pero tiene un mal response time.

#### Incorporando I/O
![[Pasted image 20230918192054.png]]
Una solución es tomar cada uno de los subprocesos como un proceso independiente → A se ve como A1, A2, A3 y A4
- Ejemplo 2 - v1 
	- ![[Pasted image 20230918192127.png]]
	- ![[Pasted image 20230918192133.png]]
#### ¿Qué pasa si no sabemos el tiempo de ejecución?

### Multi-level feedback queue
- MLFQ: “Predecir” el futuro dado el pasado reciente
- Se basa en múltiples colas de procesos, cada una con diferente prioridad 
- → al momento de ejecutar un proceso, se elige de la cola con mayor prioridad
- La prioridad se asigna según el comportamiento observado del proceso en ejecuciones anteriores y en la actual.

- #### Reglas
	- Regla 1: Si Prioridad(A) > Prioridad(B), A es ejecutado (B no aún).
	- Regla 2: If Prioridad(A) == Prioridad(B), A & B son ejecutados usando RR.
	- Regla 3: cuando un trabajo ingresa al sistema, se coloca en la prioridad más alta.
	- Regla 4a: si un trabajo consume un segmento de tiempo completo mientras se ejecuta, su prioridad es reducida.
	- Regla 4b: si un trabajo abandona la CPU antes de que el segmento de tiempo se haya actualizado, permanece en el mismo nivel.
- Ejemplo 3
	- Un proceso solitario y que ocupa mucho tiempo, ¿Cómo se comporta con MLFQ? Asumamos que hay solamente tres niveles de prioridad.
	- ![[Pasted image 20230918192556.png]]
- Ejemplo 4
	- Supongamos que en el ejemplo anterior llega un proceso
	- ![[Pasted image 20230918192636.png]]
- Ejemplo 5
	- Supongamos que en el ejemplo 3 llega un proceso, pero que es intensivo en I/O
	- ![[Pasted image 20230918193424.png]]
	- Luego de atender la interrupción, vuelve a iniciar con máxima prioridad ya que se considera un proceso nuevo cada vez que interrumpe
#### Fallas 
1.  Hambruna (starvation) 
	- a. Muchos procesos con I/O frecuente 
2. “Ganarle al sistema” 
	- Tunear el proceso de forma que la prioridad nunca baje 
3.  Un proceso puede cambiar su comportamiento durante su ejecución
#### Priority boost
- Regla 5: Después de un período de tiempo S, mueva todos los trabajos en el sistema a la cola de mayor prioridad.
- ![[Pasted image 20230918193806.png]]
#### Nueva Regla 4: 
- Una vez que un trabajo consume su asignación de tiempo en un nivel dado (independientemente de cuántas veces haya renunciado a la CPU), su prioridad se reduce.

#### Resumen 
- Regla 1: Si Prioridad(A) > Prioridad(B), A es ejecutado. 
- Regla 2: If Prioridad(A) == Prioridad(B), A & B son ejecutados usando RR. 
- Regla 3: cuando un trabajo ingresa al sistema, se coloca en la prioridad más alta. 
- Regla 4: una vez que un trabajo consume su asignación de tiempo en un nivel dado su prioridad se reduce. 
- Regla 5: Después de un período de tiempo S, todos los trabajos en el sistema se mueven a la cola de mayor prioridad.