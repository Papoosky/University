## Threads

- Una forma de paralelizar un proceso en ejecución sin crear otros procesos
- Aplicación o programa multi-thread

- #### Multi-Thread Program
	- Más de un punto de ejecución
	- Múltiples Program Counters (cada hilo tiene un contador de programa)
	- Todos comparten un mismo espacio de direcciones
- #### Implementación
- Biblioteca: pthread -> POSIX threads
1. Crear un nuevo thread
	 - ![[Pasted image 20230922215946.png]]

```  c title:thread_1.c
#include <stdio.h>
#include <pthread.h>
 
typedef struct myarg_t {
	int a; 
	int b;
} myarg_t;
 
void *mythread(void *arg) { //toma los argumentos y los imprime por pantalla
	myarg_t *m = (myarg_t *) arg;
	printf("%d %d\n", m->a, m->b);
	return NULL;
}
 
int main(int argc, char *argv[]) {
	pthread_t p;
	int rc;
 
	myarg_t args; //se invoca al struct (args es de tipo struct)
	args.a = 10;
	args.b = 20;
	rc = pthread_create(&p, NULL, mythread, &args); //NULL mo hay atributos, mythread es la función que va a ejecutar el hilo, la función mythread llevará los argumentos &args
  printf("Hola mundo\n");
  return 0;
}
//Resultado
//Hola mundo
//Parámetros: 10 20
```
2. Esperar a que un thread termine
	- ![[Pasted image 20230922230110.png]]
```  c title:thread_2.c
 #include <stdio.h>
 #include <pthread.h>
 #include <assert.h>
 #include <stdlib.h>
 
 typedef struct myarg_t {
     int a;
     int b;
 } myarg_t;
 
 typedef struct myret_t {
     int x;
     int y;
 } myret_t;
 
 void *mythread(void *arg) {
     myarg_t *m = (myarg_t *) arg;
     printf("Parámetros: %d %d\n", m->a, m->b);
     myret_t *r = malloc(sizeof(myret_t));
     r->x = 1;
     r->y = 2;
     return (void *) r;
 }

int main(int argc, char *argv[]) {
     int rc;
     pthread_t p;//inizalizacion del hilo
     myret_t *m;//puntero que apunta a tipo struct myret_t
     
     myarg_t args;
     args.a = 10;
     args.b = 20;
     pthread_create(&p, NULL, mythread, &args);
     printf("Hola mundo\n");
     pthread_join(p, (void **) &m);//aqui esperamos que el hilo termine la ejecución y tenga el resultado en m
     printf("Resultado: %d %d\n", m->x, m->y);
     return 0;
 }
 //Resultado
 //Hola mundo
 //Parámetros: 10 20
 //Resultado: 1 2
```

- #### Content-switch
	- Cada thread tiene su propio contador de programa y un conjunto de registros. 
	- Se necesitan uno o más bloques de control de threads (TCB) para almacenar el estado de cada thread.
	- Al cambiar de ejecutar de un thread (T1) a otro (T2): 
		- El estado de registro de T1 se guardará. 
		- El estado de registro de T2 será cargado. 
		- El espacio de direcciones sigue siendo el mismo.
- ![[Pasted image 20230922231052.png]]
- Stack: Donde se guarda info de variables locales, argumentos de rutinas, valores de retorno
- Heap: Estructura de datos dinamina, ej malloc 
- 2 hilos, cada hilo tiene su propio stack 

- #### Condiciones de borde (Race conditions)
	- Supongamos que tenemos un programa que desea sumar uno a un número inicial n veces. En vez de hacerlo con un ciclo lo queremos hacer con threads → cada thread le suma una unidad al número inicial ¿Qué puede pasar?
	- Resultado depende de que hilo se ejecuta primero 
- #### Sección crítica (critical section)
	- Un trozo de código que accede a una variable compartida y no debe ser ejecutado simultáneamente por más de un thread. 
		- Múltiples threads que ejecutan una sección crítica pueden dar como resultado una condición de borde. 
		- Necesidad de implementar atomicidad para secciones críticas (exclusión mutua)   -> Si es que dos hilos quieren acceder a la sección crítica entonces que entren de a uno a la vez 
- #### Locks
	- Mecanismo que ejecuta una sección crítica como si fuera una sola instrucción (atomicidad)
	- ![[Pasted image 20230922232011.png]]
	- `lock(&mutex); //bloqueando acceso a 'balance'
	- `unlock(&mutex); //liberando acceso a 'balance'
	- La variable de tipo lock mantiene el estado de la sección crítica:
		- Available (Free, Unlocked) 
		- Acquired (Locked, Held)
	- ##### ¿Cuándo usar locks?
		- Exclusión mutua 
			- ¿Funciona el bloqueo, evitando que múltiples hilos entren en una sección crítica? 
		- Justicia 
			- ¿Cada hilo que compite por la cerradura tiene una buena oportunidad de adquirirlo una vez liberado? (Hambruna) 
		- Rendimiento 
			- Los gastos generales de tiempo agregados al usar el bloqueo
	- ##### Implementaciones iniciales (no hacer):
		- Deshabilitar interrupciones → Nadie me quita el control mientras estoy en una sección crítica
		- ![[Pasted image 20230923184752.png]]
	 - Problemas?
		- No sirve en sistemas con múltiples procesadores 
		- Código que bloquea interrupciones es ejecutado con baja prioridad en CPUs modernas 
		- Hay que confiar en la app
	- ##### Flags:
		- ![[Pasted image 20230923184809.png]]
	- ##### Soporte en hardware
		- Instrucciones test-and-set
		- ![[Pasted image 20230923192705.png]]
		- ![[Pasted image 20230923192712.png]]
		- Exclusión mutua: Sí
		- Justicia: No 
			- Un thread puede estar en busy waiting por siempre 
			- Busy waiting no es eficiente 
		- Rendimiento: No 
		- En una sola CPU el rendimiento es pésimo 
		- Si número de CPUs == número de Threads → OK
	- ##### Compare and swap
		- Comparo el valor del lock con uno que espero 
			- Si es igual → cambio a nuevo valor 
			- Retorno el valor final
			- ![[Pasted image 20230923192859.png]]
			- ![[Pasted image 20230923192906.png]]
	- ##### Load-Linked y Store-Conditional
		- Similar a Compare-And-Swap, pero primero obtengo una referencia a una variable
		- ![[Pasted image 20230923192938.png]]
		- ![[Pasted image 20230923192945.png]]
		- ##### Ticket Lock
			- Fetch-And-Add:Incrementar atómicamente el valor de una variable en una dirección en particular
			- ![[Pasted image 20230923193005.png]]
			- ![[Pasted image 20230923193018.png]]
	- ##### ¿Cómo evitamos el busy waiting?
		- ##### YIELD
			- Si voy a entrar a un ciclo, delego el control de la CPU
			- ![[Pasted image 20230923193103.png]]
	- ##### ¿Problemas?
		- Una cola para saber qué threads desean usar una sección crítica 
			- park(): pone a “dormir” un thread. 
			- unpark(threadID): despierta el thread con id igual a threadID.
			- ![[Pasted image 20230923193205.png]]
			- ![[Pasted image 20230923193214.png]]
- ### Implementación 
	- ![[Pasted image 20230923200447.png]]
	- ![[Pasted image 20230923200457.png]]
	- ![[Pasted image 20230923200503.png]]
	- ![[Pasted image 20230923200509.png]]
	- ![[Pasted image 20230923200514.png]]
	- ![[Pasted image 20230923200522.png]]
	- ![[Pasted image 20230923200527.png]]
	- ![[Pasted image 20230923200531.png]]