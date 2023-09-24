### Ejecución directa
- Dos procesos en la CPU (P1y P2), de tiempo 4, y el proceso P1 está ejecutando. Si la regla del scheduler es que el proceso termine antes de procesar el siguiente ¿Qué pasa?
- ![[Pasted image 20230911124412.png]]
- Proceso que llega a la CPU desocupada se ejecuta de inmediato y queda con el poder hasta que termine
### Enfoque cooperativo 

- Mismo ejemplo anterior, pero ahora el proceso P1 debe usar un dispositivo (como la impresora) en el tiempo 3, que toma 3 tiempos ¿Qué pasa?
- ![[Pasted image 20230911124818.png]]
- El segundo ejemplo nos muestra un caso en que un proceso “cede” la CPU a otro por alguna razón. El SO confía en que esto pasará seguido.

--> Reiniciar el computador lo hace volver a un estado conocido y probado 

### ¿Qué debería hacer el SO cuando esto ocurre?

- Interrupción por timeout
	- Timer interrupt es la manera que el SO tiene para lograr recuperar el control de la CPU
	- Funcionamiento -> Al iniciar, el SO le dice a la CPU que ejecutar cuando ocurra un timeout E inicializa el timer que controla el tiempo Luego cuando un programa se ejecuta, si ocurre un timer, se realiza un context switch y el control se pasa a otro proceso
	- ![[Pasted image 20230912105630.png]]

### ¿Qué pasa si ocurren 2 interrupciones al mismo tiempo?

1. Deshabilitar interrupciones
2. Mecanismo de locking (candado)
