## Gestores de contraseña

- <mark style="background: #FFF3A3A6;">Herramienta diseñada para ayudarte a gestionar y proteger tus contraseñas de forma segura.</mark> Su principal objetivo es simplificar y mejorar la seguridad de tus cuentas en línea y datos personales.

## Multifactor Autentication

- La autenticación de múltiples factores (MFA, por sus siglas en inglés) es una técnica de seguridad informática que se utiliza para proteger cuentas y sistemas al requerir que los usuarios proporcionen <mark style="background: #FFF3A3A6;">múltiples formas de autenticación antes de acceder a una cuenta o recurso en línea.</mark> Su principal objetivo es aumentar la seguridad al agregar una capa adicional de protección más allá de la simple contraseña.

## Blockchain

- Blockchain es una tecnología de registro distribuido (DLT) que se utiliza para <mark style="background: #FFF3A3A6;">mantener un registro seguro y verificable de transacciones o eventos.</mark> En lugar de tener una autoridad central que administre y valide estas transacciones, blockchain permite que <mark style="background: #FFF3A3A6;">múltiples participantes en una red descentralizada verifiquen y validen las transacciones de manera consensuada.</mark>
- Una red blockchain consiste en una serie de nodos de red (computadoras) que se distribuyen en todo el mundo. Estos nodos pueden ser operados por individuos, organizaciones o empresas.
- Cuando alguien realiza una transacción en la red blockchain, esta se transmite a través de la red a todos los nodos.
- Los nodos de la red trabajan en conjunto para validar y verificar la transacción
- ![[Pasted image 20230923103043.png]]
- ![[Pasted image 20230923103050.png]]
- Cada bloque contiene un grupo de transacciones. Los bloques están vinculados entre sí en una cadena, de ahí el nombre "blockchain".
- Una vez que un bloque se agrega a la cadena, es extremadamente difícil modificar o eliminar cualquier información en él. Esto se debe a que <mark style="background: #FFF3A3A6;">cada bloque contiene una referencia al bloque anterior (hash del bloque anterior). </mark>Cambiar cualquier información en un bloque requeriría cambiar todos los bloques posteriores, lo que sería prohibitivamente costoso y requeriría el consenso de la mayoría de la red, lo que hace que la cadena sea inmutable y segura contra la manipulación.

## HTTPS

Protocolos de seguridad que se utilizan en la capa de transporte para proporcionar comunicaciones seguras en línea a través del protocolo HTTPS
- ### SSL (**Secure Sockets Layer**)
	- Primer protocolo de seguridad utilizado para garantizar la confidencialidad y la integridad de los datos transmitidos a través de la web.
	- Utiliza algoritmos de cifrado para proteger los datos transmitidos entre un cliente (como un navegador web) y un servidor web. Estos algoritmos <mark style="background: #FFF3A3A6;">garantizan que los datos no puedan ser leídos o alterados por terceros mientras viajan por Internet.</mark>
	- Sin embargo, con el tiempo, se descubrieron vulnerabilidades en SSL, como POODLE y BEAST, que llevaron a su desuso gradual en favor de TLS.
- ### TLS (**Transport Layer Security**)
	- TLS es el sucesor de SSL y representa una versión más segura y avanzada de los protocolos de seguridad en línea.
	- Al igual que SSL, TLS proporciona <mark style="background: #FFF3A3A6;">autenticación, confidencialidad e integridad de los datos transmitidos a través de la web</mark>, pero utiliza algoritmos de cifrado más robustos y seguros.
	- TLS también incluye características de negociación de protocolos para garantizar que ambas partes (cliente y servidor) acuerden un conjunto de cifrado y protocolos de seguridad compatibles antes de establecer una conexión segura.

## Modelo OSI

![[Pasted image 20230923133452.png]]

#### 1. Capa 1 (Capa Física):
- Esta capa se encarga de las características físicas de la transmisión de datos, como el <mark style="background: #FFF3A3A6;">medio de transmisión</mark> (cables, fibra óptica, aire), voltajes, velocidades de transmisión y topología de la red. Define cómo se envían y reciben los bits.
#### 2. Capa 2 (Capa de enlace de datos):
- La capa de enlace de datos maneja la comunicación directa entre dispositivos conectados en la misma red física. Se encarga de la <mark style="background: #FFF3A3A6;">detección y corrección de errores, el control de flujo y la dirección física (MAC).</mark>
#### 3. Capa 3 (Capa de red):
- La capa de red se ocupa del <mark style="background: #FFF3A3A6;">enrutamiento de datos a través de la red</mark>. Define cómo se determina el mejor camino para transmitir datos desde el origen al destino, utilizando direcciones IP. El enrutador es un dispositivo típico de esta capa.
#### 4. Capa 4 (Capa de transporte):
- La capa de transporte asegura la <mark style="background: #FFF3A3A6;">entrega confiable de datos entre dispositivos finales.</mark> Controla la segmentación, el flujo y la reordenación de datos, y puede proporcionar tanto conexiones orientadas como no orientadas a la conexión. Protocolos como TCP (Control de Transmisión) y UDP (Protocolo de Datagrama de Usuario) operan en esta capa.
#### 5. Capa 5 (Capa de Sesión):
- La capa de sesión <mark style="background: #FFF3A3A6;">establece, mantiene y finaliza las conexiones entre dos dispositivos.</mark> También maneja la sincronización y el control de diálogo entre las aplicaciones.
#### 6. Capa 6 (Capa de presentación):
- La capa de presentación se encarga de la <mark style="background: #FFF3A3A6;">traducción, compresión y cifrado de datos para garantizar que los dispositivos puedan entenderse entre sí. </mark>También se ocupa de la representación y conversión de datos entre diferentes formatos.
#### 7. Capa 7 (Capa de aplicación):
- La capa de aplicación es la capa superior y más cercana al usuario. Aquí es donde operan las aplicaciones y servicios de usuario final. Incluye protocolos de alto nivel para servicios como correo electrónico (SMTP), navegación web (HTTP), transferencia de archivos (FTP) y más.

## Microsegmentación por MAC ADDRESS
- Técnica de seguridad de redes que se utiliza para <mark style="background: #FFF3A3A6;">dividir una red en segmentos más pequeños y gestionar el tráfico de forma más granular a nivel de direcciones MAC.</mark> En lugar de depender únicamente de direcciones IP, la microsegmentación se basa en las direcciones MAC de los dispositivos conectados a la red para aplicar <mark style="background: #FFF3A3A6;">políticas de seguridad específicas y controlar el acceso a recursos.</mark>

## VLANs

![[Pasted image 20230923134724.png]]

- Son una tecnología de redes que permite <mark style="background: #FFF3A3A6;">dividir una red local física en múltiples redes lógicas o segmentos virtuales.</mark> Estas redes lógicas funcionan como si fueran redes físicas independientes, aunque comparten la misma infraestructura física subyacente, como cables y conmutadores (switches). Las VLAN ofrecen varios beneficios, incluida la segmentación de la red, el aislamiento de tráfico y una mayor flexibilidad en la gestión de redes.
- Por ejemplo, en una empresa, se pueden crear VLAN separadas para los departamentos de ventas, marketing y desarrollo, lo que permite un mejor aislamiento y administración del tráfico.

## Subredes

![[Pasted image 20230923135737.png]]
- La creación de subredes es una técnica fundamental en la gestión de redes y se utiliza para varios propósitos, como la <mark style="background: #FFF3A3A6;">optimización de la administración de direcciones IP, el aislamiento de tráfico, la mejora de la seguridad y la organización de una red en subgrupos lógicos.</mark>
- Las subredes permiten dividir el espacio de direcciones IP en bloques más pequeños. Esto es útil para asignar direcciones IP de manera eficiente a dispositivos en una red y evitar el agotamiento de direcciones en una red grande.
## Private link

![[Pasted image 20230923135900.png]]

- Permite a los clientes acceder a los servicios en la nube de forma segura y privada a través de una conexión de red privada en lugar de a través de Internet público.
- La idea fundamental detrás de Private Link es aislar y asegurar el tráfico entre la infraestructura de la nube y los recursos de un cliente, lo que reduce la exposición a amenazas de seguridad y mejora la privacidad de los datos.

## ExpressRoute

![[Pasted image 20230923140116.png]]

![[Pasted image 20230923140129.png]]

- Permite a las organizaciones establecer conexiones de red dedicadas y privadas entre sus redes locales y la infraestructura de la nube de Azure. Este servicio proporciona una conectividad de red de alto rendimiento, segura y de baja latencia que permite a las organizaciones aprovechar los recursos y servicios de Azure de manera eficiente y confiable.
- ExpressRoute evita el uso de Internet público para acceder a los servicios de Azure, lo que aumenta la seguridad al aislar el tráfico de la nube de la red pública. Esto es especialmente importante para aplicaciones y datos sensibles.

## Network Security Group

- ![[Pasted image 20230923140446.png]]

- ![[Pasted image 20230923140451.png]]
- Los NSG son grupos de seguridad virtuales que actúan como cortafuegos o firewalls a nivel de red y permiten a los administradores definir reglas para controlar el tráfico de red hacia y desde los recursos dentro de una red virtual de Azure.
- Los administradores pueden crear reglas personalizadas para permitir o denegar el tráfico en función de sus necesidades específicas. Esto incluye la especificación de rangos de direcciones IP, puertos y protocolos permitidos o prohibidos.