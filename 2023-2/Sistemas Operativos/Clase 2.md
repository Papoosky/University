- ### Procesos
	- Una de las abstracciones más fundamentales en sistemas operativos
	- <mark style="background: #FFF3A3A6;">Definición: Es un programa en ejecución</mark>
	- Partes que conforman un proceso:
		- Estado de ejecución
		- Área temporal de datos
		- Hardware
		![[Pasted image 20230910135641.png]]
	-  Un programa en ejecución se debe almacenar en memoria, el estado de este, los datos, etc.

- Un proceso guarda en memoria: 
	- Código (text)
	- Datos (Data)
	- Variables y estado programa (Stack/ Heap)
![[Pasted image 20230910140840.png]]

- El espacio de direcciones es la representación en memoria de un proceso 
- V0 -> Vmax : Direcciones virtuales del proceso 
	- No corresponden a direcciones reales en la memoria física del computador
	- Page table contiene el mapeo entre ambas 

- ### Ejecución de un proceso
	- #### Program Counter (PC) 
		- Es un registro del procesador de un computador que indica la posición donde está el procesador en su secuencia de instrucciones.
	- #### CPU Registers
		- Es una memoria de alta velocidad y poca capacidad, integrada en el microprocesador, que permite guardar transitoriamente y acceder a valores muy usados,
	- #### Stack Pointer
		- Registro apuntador a la posición de memoria donde se encuentra la pila
- ### Program Control Block 
	- <mark style="background: #FFB86CA6;">Estructura de datos que el SO mantiene para cada proceso</mark> 
		- Creada cuando el proceso es creado
		- Actualizado cuando el proceso cambia
			- Poco frecuente
			- Frecuente -> CPU register
			- ![[Pasted image 20230911112758.png]]
- ### Context Switch
	- Mecanismo usado por el SO para cambiar en la CPU el contexto de un proceso por el de otro 
	- Es una operación cara:
		- Almacenar y cargar los datos
		- Cold cache
		- -> Limitar context switches 
- ### Estados de un proceso 
	- ![[Pasted image 20230911113052.png]]


- ### Creación de un proceso 
	1. El programa se encuentra en forma estática en disco
	2. Se carga en memoria del código y datos estáticos
	3. Asigna memoria para el heap y stack
	4. Inicializa el stack con los valores de los parámetros del programa(argv, argc)
	5. Inicializa el I/O del proceso 
		- Por lo menos con stdin, stdout, stderr
	6. Va al punto de inicio del programa(main)
	- 2 maneras típicas:
		- Fork: Crea un proceso hijo con el mismo PCB del padre (duplicación)
		- Exec: Cambia la imagen a ejecutar por un nuevo programa
``` c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
int main() {
    printf("hola mundo (pid:%d)\n", (int) getpid());
    int rc = fork();
    if (rc < 0) {
        fprintf(stderr, "error\n"); 
        exit(1);
    } else if (rc == 0) {
        // hijo (nuevo proceso)
        printf("hola, soy el hijo (pid:%d)\n", (int) getpid());
    } else {
        // padre (proceso original)
        printf("hola, soy el padre de %d (pid:%d)\n", rc, (int) getpid());
    }
    return 0;
}
//resultado
//hola mundo (pid:1445)
//hola, soy el padre de 1446 (pid:1445)
//hola, soy el hijo (pid:1446)
``` 

- ### System calls
	- Destruir proceso (kill)
	- Pausar/ Reanudar
	- Estado
	- wait()
	- fork() : inicia un nuevo proceso que es una copia del que lo llama
	- exec() : reemplaza la imagen del proceso actual por otra (diferente).

- ### CPU Scheduler
	- Decide qué proceso va a ser asignado a la  CPU y cuanto rato va a estar asignado 
		- Puede interrumpir la ejecución si el tiempo pasa 
		- Schedule
		- Dispatch
		- ![[Pasted image 20230911122801.png]]

### Ejemplos 
- Dos procesos en la CPU (P1y P2), de tiempo 4, y el proceso P1 está ejecutando. Si la regla del scheduler es que el proceso termine antes de procesar el siguiente ¿Qué pasa?
	- ![[Pasted image 20230911122900.png]]
- Mismo ejemplo anterior, pero ahora el proceso P1 debe usar un dispositivo (como la impresora) en el tiempo 3, que toma 3 tiempos ¿Qué pasa?
	- ![[Pasted image 20230911122920.png]]

### Estructura de datos (XV6)
- #### UNUSED: 
	- Este estado indica que el proceso ha sido creado pero aún no se ha inicializado o utilizado. Es decir, el sistema operativo ha reservado recursos para el proceso, pero aún no se ha ejecutado.

- #### EMBRYO: 
	- Este estado es un paso más avanzado que UNUSED. Significa que el proceso está en proceso de inicialización. A menudo, implica la asignación de recursos y la configuración inicial antes de que el proceso esté listo para ejecutarse.

- #### SLEEPING: 
	- Un proceso en estado SLEEPING está esperando a que ocurra algún evento o se cumpla alguna condición antes de continuar su ejecución. Esto podría ser esperar una entrada de usuario, una señal de otro proceso o una operación de entrada/salida que esté pendiente.

- #### RUNNABLE: 
	- Un proceso en estado RUNNABLE está listo para ejecutarse en cuanto el planificador del sistema operativo le asigne tiempo de CPU. Está en cola para ser ejecutado y espera su turno.

- #### RUNNING: 
	- Este estado indica que el proceso actualmente se está ejecutando en la CPU. En un momento dado, solo puede haber un proceso en estado RUNNING en un núcleo de CPU.

- #### ZOMBIE: 
	- Cuando un proceso ha terminado su ejecución, pasa al estado ZOMBIE. En este estado, todavía mantiene algunos recursos y su entrada en la tabla de procesos, pero la mayor parte de sus recursos se han liberado. El estado ZOMBIE es temporal y generalmente se utiliza para permitir que el proceso padre obtenga información sobre la finalización del hijo antes de que el proceso hijo sea completamente eliminado del sistema.
