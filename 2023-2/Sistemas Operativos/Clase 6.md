## Semáforos

- Una alternativa a la mezcla de Locks con variables condicionales Propuesto por Dijkstra como una primitiva en Sistemas Operativos
- Un semáforo es un objeto con un 
valor entero que podemos 
manipular. En POSIX:
- sem_wait() ~ Lock
- sem_post() ~ Unlock
### Implementación de POSIX

- #### Inicialización
	- ![[Pasted image 20230923202950.png]]
	- Segundo argumento:
		 - // Hilos -> 0
		- //Procesos -> 1
	- Tercer argumento:
		- S = 1
	- ![[Pasted image 20230923203056.png]]
	- ![[Pasted image 20230923203113.png]]
	- El número negativo que resulta de sem_wait indica la cantidad de threads esperando 
	- sem_wait es una operación que bloquea, sin embargo sem_post no
### Semáforos Binarios (Locks)

- ![[Pasted image 20230923203412.png]]
- ![[Pasted image 20230923203446.png]]
- ![[Pasted image 20230923203513.png]]
- Thread 1 no puede acceder a la sección crítica porque ya estaba reservada
- Los semáforos pueden usarse para ordenar la ejecución de instrucciones 
	- Por ejemplo, si alguien quiere borrar un elemento de una lista entonces primero tiene que haber al menos un elemento
```  c title:forkwait_en_threads.c
#include <stdio.h>
#include <pthread.h>
#include <semaphore.h>

sem_t s;

void* elhijo(void* arg) {
  printf("buenas buenas, aqui el hijo\n");
  sem_post(&s); // señal de que está listo
  return NULL;
}

int main(void) {
  sem_init(&s, 0, 0); //si se pone 1 no se ejecuta el hijo
  printf("el padre comenzando\n");
  pthread_t c;
  pthread_create(&c, NULL, elhijo, NULL);
  sem_wait(&s); // espera a que el hijo se ejecute
  printf("el padre finalizando\n");
  return 0;
}
```

![[Pasted image 20230923205246.png]]
![[Pasted image 20230923205251.png]]
