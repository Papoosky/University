## Esteganografía 
- Arte de esconder información.
- <mark style="background: #FFF3A3A6;">Busca ocultar el hecho de que se esta transfiriendo información del todo.</mark>
- Ejemplos
	- Cera en tablas talladas de madera
	- Cuero cabelludo de esclavos
	- Incrustación de textos en archivos JPEG
## Criptografía 
- Es el estudio de las técnicas de protección de la comunicación entre 2 partes en presencia de terceros (adversarios).
- <mark style="background: #FFF3A3A6;">Busca ocultar el mensaje, no el hecho de que se está enviando uno</mark> (a diferencia de la esteganografía).

### Cifrado Simétrico
- <mark style="background: #FFF3A3A6;">Utiliza una única llave de cifrado (encryption key), para cifrar los datos que se requieran.</mark> Para lograr cifrar algo se utilizan algoritmos, en este caso, “algoritmos de cifrado simétro”, comúnmente denominados cipher aunque la palabra puede interpretarse como cualquier tipo de cifrado, no solo el simétrico. Denominamos en adelante <mark style="background: #FFF3A3A6;">plaintext a la información o datos que deseamos cifrar</mark> (esto puede ser audios, imágenes, videos, no solo texto). Una vez cifrado lo llamaremos <mark style="background: #FFF3A3A6;">ciphertext</mark>, aunque muchas veces no se verá como texto.
- En el cifrado simétrico, se utiliza la <mark style="background: #FFF3A3A6;">misma clave tanto para cifrar como para descifrar los datos.</mark> Esta clave se conoce como "clave de cifrado" o "clave secreta". Tanto el <mark style="background: #ABF7F7A6;">remitente como el receptor deben conocer esta clave para comunicarse de manera segura.</mark>
- El más utilizado hoy en día es AES.
- Paso a paso: 
	1. Escoger un algoritmo de cifrado (cipher). 
	2. Generar una llave de cifrado. 
	3. Generar un vector de inicialización (IV - initialization vector). 
	4. Escoger el modo de operación del cipher.
	5. Escoger un padding type. 
	6. Encrypt the plaintext.
- #### Block ciphers vs Stream ciphers
	- ##### Block ciphers: 
		- AES es uno de los ciphers más famosos que utilizan Block cipher. En este caso el tamaño máximo de los datos a cifrar es de 128 bits, si fuera más grande el plaintext, deberá separarse en bloques más pequeños.
		- ![[Pasted image 20230919163720.png]]
	- ##### Stream ciphers:
		- Actua bit a bit (o byte a byte), por lo que no necesita padding y por ahora no requieren de especificar un modo de operación. Esto lo hace ser más sencillo de utilizar y resulta ser más rápido. Se utiliza sobretodo en streaming por esta última razón.
		- *Especialistas del área aseguran que es menos seguro que Block cipher.
		- ![[Pasted image 20230919164223.png]]
#### Paso 4: Modo de operación del cipher
- ##### Electronic Code Book / ECB:
	- ![[Pasted image 20230919164927.png]]
	- Cada bloque de datos de entrada se cifra de forma independiente utilizando la misma clave. Esto significa que si dos bloques idénticos de datos se cifran con la misma clave, producirán el mismo resultado cifrado. Esto puede ser una vulnerabilidad en ciertos casos, ya que un atacante puede detectar patrones en los datos cifrados y obtener información sobre la estructura de los datos originales.
- ##### Cipher Block Chain / CBC
	- ![[Pasted image 20230919170410.png]]
	- Los datos de entrada se dividen en bloques de un tamaño fijo (por ejemplo, 128 bits) antes de ser cifrados.
	- Antes de cifrar el primer bloque, se utiliza un IV, que es un valor aleatorio único para cada mensaje o sesión de cifrado. El IV se combina con el primer bloque de datos mediante una operación XOR.
	- Cada bloque de datos se cifra utilizando la clave de cifrado, al igual que en un block cipher convencional, como AES. La diferencia principal es que el resultado del cifrado se combina con el bloque siguiente antes de cifrarlo.
	- Después de cifrar cada bloque de datos, se realiza una operación XOR (exclusiva OR) con el bloque cifrado anterior. Esto significa que el cifrado de cada bloque depende del contenido del bloque anterior, lo que introduce confusión y evita la propagación de patrones en los datos cifrados.
	- Para descifrar, se aplica el proceso inverso. Cada bloque cifrado se desenlaza del bloque cifrado anterior mediante una operación XOR y luego se descifra utilizando la misma clave de cifrado. El IV se utiliza para desenlazar el primer bloque cifrado.
- ##### Counter (CTR)
	- ![[Pasted image 20230919174931.png]]
	- Antes de cifrar, se genera un contador único para cada bloque de datos a cifrar. Este contador generalmente se combina con un valor inicial llamado "nonce" (número usado una sola vez), que también debe ser único para cada cifrado. La combinación del nonce y el contador se utiliza como entrada para un cifrador simétrico, como AES, para generar una clave de flujo (keystream).
	- Una vez que se ha generado el keystream, se realiza una operación XOR entre el keystream y los datos originales. Esta operación XOR se realiza bit a bit o byte a byte, lo que permite cifrar los datos en tiempo real a medida que se transmiten o procesan. La operación XOR es reversible, lo que significa que para descifrar, simplemente se realiza la misma operación XOR entre el keystream y los datos cifrados.
	- A diferencia de los modos de operación como CBC, en CTR no hay dependencia entre los bloques de datos cifrados. Cada bloque se cifra de manera independiente y no hay necesidad de realizar operaciones complejas de encadenamiento.
- ##### Galois/Counter mode or GCM
	- ![[Pasted image 20230919232052.png]]
	- GCM utiliza el modo de operación Counter (CTR) para cifrar los datos.
	- GCM incorpora un mecanismo de autenticación. Utiliza el Código de Autenticación de Mensaje de Galois (GMAC) para generar una etiqueta de autenticación. Esta etiqueta se calcula utilizando el texto cifrado y un dato adicional llamado "Datos Asociados" (AD), que puede utilizarse para autenticar metadatos o encabezados, además de los datos reales.
	- GCM requiere un Vector de Inicialización (IV) único para cada operación de cifrado. El IV nunca debe reutilizarse con la misma clave de cifrado. El IV se combina con el contador para crear contadores únicos para cada bloque de datos.
- ##### Antiguos algoritmos aún en uso
	- DES
	- 3DES
	- RC4
	- ChaCha20

### Cifrado Asimétrico
- En el cifrado asimétrico, se utilizan dos claves distintas pero relacionadas: una <mark style="background: #FFF3A3A6;">clave pública y una clave privada.</mark> <mark style="background: #ABF7F7A6;">La clave pública se utiliza para cifrar datos, mientras que la clave privada se utiliza para descifrarlos.</mark> La clave privada debe mantenerse en secreto, mientras que la clave pública puede ser compartida públicamente.
- ![[Pasted image 20230919233719.png]]
- ![[Pasted image 20230919233743.png]]

### Hashes
- <mark style="background: #FFF3A3A6;">Una función criptográfica de hash es un algoritmo que entrega siempre un resultado de tamaño único</mark> y conocido el cual denominamos cryptographic hash or message digest.
- Dentro de las propiedades se destaca que es un algoritmo determinístico <mark style="background: #FFF3A3A6;">(con un mismo input siempre tendrán el mismo output</mark>), irreversible, debe ser computacionalmente inviable encontrar dos message digest iguales, en caso de encontrarlos estaríamos frente a una colisión de hash, y finalmente pero no menos importante, cualquier cambio chico o grande al plaintext, debe resultar en una notoria modificación del hash, lo cual se denomina efecto avalancha. Esto se utiliza para asegurar la integridad de los datos.
- #### Algoritmos
	- El más popular hoy en día es SHA-2, con opciones de 256 y 512 bits. Ya existe un SHA3, pero aún se necesita un hardware específico para que los tiempos de ejecución sean menores a SHA-2.
	- La NSA creó el SHA-1 en 1990, muchísimo más rápido que su predecesor MD5, pero ya en 2017 se encontró su primera colisión. Pasando entonces a formar parte de la lista de algoritmos no recomendados. Rusia por otro lado tiene sus propios algoritmos, bajo el nombre clave GOST94 fue desclasificado en 1994 y tiene un sucesor nombrado GOST2012 o GOST12. China utiliza SM3, muy similar a SHA-256, con un nivel de seguridad de 128 bits.