
## Virtualización en memoria
- El computador tiene una cantidad de memoria (RAM) limitada físicamente, sin embargo, el sistema operativo simula una memoria infinita para albergar muchos procesos
- ### Funcionamiento
	- Espacio de memoria para cada proceso
	- Cada proceso piensa que tiene acceso único a toda la memoria del computador
	- #### Beneficios:
		- Facilidad de uso al programar (API)
		- Eficiencia en memoria en relación a tiempo y espacio
		- Aislamiento → Protección
	- #### En un principio:
		- Toda la memoria a un proceso
		- No era eficiente
		- No utilizaba el espacio en forma adecuada
		- ![[Pasted image 20231109175417.png]]
		- #### Multiprograming:
			- Cargar múltiples procesos
				- Incrementar utilización
				- Permite context switch → eficiencia
			- Sin protección
				- Procesos pueden acceder a otros espacios de memoria
			- ![[Pasted image 20231109175531.png]]
- ## Espacio de direcciones
	- OS crea una abstracción de la memoria física
	- TODAS las direcciones de memoria en un proceso SON VIRTUALES
		- Contiene toda la información del proceso
		- Está dividida en secciones: text, data, heap, stack
			- Text (code): donde está el código del programa
			- Data: donde se guardan los valores estáticos (no cambian durante ejecución) o globales
			- Heap: memoria asignada dinámicamente
			- Stack: datos de métodos, direcciones de retorno, valores
		- ![[Pasted image 20231109175651.png]
```c title:test.cpp 
int main(int argc, char* argv[]){ 
	printf("location of text : %p\n", (void*) main); 
	static int sttc = 2; 
	printf("loc of data : %p\n", (void*) &sttc);
    printf("loc of heap : %p\n", (void*) malloc(1)); int x = 3;        printf("location of stack : %p\n", (void*) &x); 
    return EXIT_SUCCESS; 
}

```
- ## API de memoria
	- ### Malloc: 
		- Asignar memoria dinámicamente
		- Incluir (para este y todas los otros métodos): # include<stdlib.h>
		- Definición: void* malloc(size_t size) 
		- size_t size = Tamaño de la memoria solicitada
	- ### Calloc: 
		- Asignar memoria dinámicamente e inicializarla en ceros
		- Definición: void* calloc(size_t num, size_t size)
		- num = Número de bloques de memoria solicitada
		- size = Tamaño de los bloques de memoria solicitada
	- ### Free:
		- Liberar memoria asignada dinámicamente
		- Definición: void free(void* ptr)
	- ### Realloc: 
		- Cambia el tamaño de memoria asignado a un puntero
		- Definición: void* realloc(void* ptr, size_t size)
		- void* ptr = Dirección de memoria (puntero)
		- size = Tamaño de memoria solicitada
	- Recordar usar malloc ANTES de usar el puntero y asignar un valor inicial
	- SIEMPRE deben liberar memoria pedida en forma dinámica
	- Al liberar memoria NO deben usar el objeto nuevamente
	- No deben liberar más de una vez
	- Free solamente se usa sobre objetos en el heap (creados dinámicamente)
	- ### Sizeof:
		- Macro para pedir memoria según un tipo de dato
		- Definición: size_t sizeof(void* t)
		- sizeof = Tamaño calculado
		- void* t = Variable o tipo de dato para el cual obtener el tamaño
- ## Llamadas de sistema
	```c title:test.cpp 
include <unistd.h>
int brk (void* addr); 
void* sbrk(intptr_t increment); 
void *mmap(void *addr, size_t len, int prot, int flags, int fildes, off_t off);
```
	- malloc usa brk/sbrk, que es básicamente una llamada al sistema operativo para que incremente el puntero que marca el término del espacio de memoria del heap y mmap para solicitar el espacio de memoria correspondiente.
- ## Traducción de direcciones
	- Toda dirección virtual tiene que pasar a una física para usar los datos almacenados Para hacer eficiente la conversión debemos usar HW
	- → El sistema operativos se encarga de tener todo configurado para el HW
	- ### Supuestos
		- El espacio de direcciones de un proceso está en un espacio contiguo de memoria física
		- El tamaño del espacio de direcciones es menor que la memoria física disponible
		- Cada espacio de direcciones tiene el mismo tamaño
		- #### Espacio de direcciones
			- Proceso cree que su espacio de direcciones parte en 0 y se extiende hasta 16kb
			- ![[Pasted image 20231109184935.png]]
		- #### Memoeria física
			- Sin embargo, para el sistema operativo, la memoria del proceso puede partir en cualquier lugar
			- ![[Pasted image 20231109185008.png]]
		- #### Reubicación dinámica
			- Idea: dos registros de CPU
				- Base: contiene la dirección de inicio en memoria física
				- Bound (limit): máximo valor de memoria (virtual o físico)
		- #### Traducción de direcciones
			- Dirección Física = Dirección virtual + base
			- Si Dirección Física no pertenece a rango
			- Entonces
				- Falla señalando que se salió del rango
			- De lo contrario
				- Retorna la dirección física
	- ### Ejemplo
		- ![[Pasted image 20231109195230.png]]
		- Dirección física = Dirección virtual + base
		- 32 bytes x 1024 = 0 + base
		- base = 32 x 1024 (32KB)
	- ### Hardware
		- Todo lo anterior se hace en hardware:
			- Modo Kernel (privilegiado)
			- Registros Base/Bound
			- Traducción a memoria física y chequeo
			- LLamadas de sistema para cambiar registros y manejar excepciones que puedan surgir
	- ### Qué hace el sistema operativo?
		1. Busca espacio libre disponible
		2. Manejar el término del proceso
			- Reclamar el espacio de memoria asignado
			- Básicamente volver a ponerlo en la lista de memoria disponible
		3. Manejar los cambios de contexto
			- Guardar y restaurar registros
		4. Proveer exception handlers
			- Funciones a llamar si la memoria sale del rango
			- Típicamente matar el proceso :)
	- ### Segmentación 
		- Coloca cada segmento en un lugar distinto de la memoria física, minimizando los espacios sin utilizar
		- ![[Pasted image 20231109200136.png]]
		- Debe existir un par de registros base/bound por cada segmento
	- ### Traducción de direcciones
		- Determina el segmento a utilizar
			- Instrucciones → program code
			- Variables con memoria asignada → heap
			- Puntos de retorno → stack
		- Luego el cálculo es Dirección Física = Dirección virtual + base - offset
	- ### ¿Cómo sé a qué segmento me refiero?
		- #### Enfoque explícito
			- Marcar con los bits iniciales el tipo de segmento
			- ![[Pasted image 20231109220753.png]]
			- ##### Problemas 
				- Espacio de direcciones sin usar
				- Tamaños fijos
		- #### Enfoque implícito
			- El SO se encarga de determinar el segmento
				- Si la instrucción anterior es un instruction fetch → program code
				- Si está basada en el stack pointer → stack
				- “Todo” el resto es el heap
	- ### Stack
		- Siempre hemos visto esta figura donde el Stack crece “hacia abajo”
		- Necesitamos un registro más: la dirección en la que crece el segmento
		- ![[Pasted image 20231109221024.png]]
		- → al hacer la traducción de direcciones debo ver si sumar o restar el offset
		- ![[Pasted image 20231109221047.png]]
	- ### Código compartido
		- En multiprocesos hay ocasiones en que se desea compartir código (como por ejemplo muchas instancias de la misma aplicación) Para maximizar el uso de memoria es posible compartir segmentos
	- ### Bits de protección
		- Si los bits de protección señalan un segmento como read-only → es posible compartirlo
		- ![[Pasted image 20231109221219.png]]
		- Ahora necesito un chequeo extra: Si la operación es de escritura en memoria y el segmento es solo de lectura → access error
	- ### Segmentación fina
		- Muchos segmentos de memoria en vez de solamente tres → Tabla de segmentos
	- ### Fragmentación externa
		- SO debe solicitar espacio en memoria para un nuevo proceso
		- Sin embargo, muchos procesos dispersaron sus segmentos, por lo que no quedan espacios contiguos de tamaño suficiente
