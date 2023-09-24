
## VPN 

- Es una tecnología que permite establecer una conexión segura y cifrada entre dos puntos a través de una red pública, como Internet. Esta conexión segura se utiliza para proteger la privacidad y la seguridad de la información transmitida entre estos dos puntos, lo que resulta útil en diversas situaciones.
- La principal función de una VPN es cifrar los datos que se transmiten a través de la conexión. Esto significa que, incluso si alguien intercepta el tráfico, no podrá entenderlo sin la clave de descifrado adecuada.
- Una VPN oculta la dirección IP real del usuario y enmascara su ubicación.
- Las VPN se utilizan comúnmente para conectarse de forma segura a redes corporativas o recursos privados desde ubicaciones remotas. Los empleados pueden acceder a recursos empresariales de manera segura, incluso cuando están fuera de la oficina.

## Bastion host

![[Pasted image 20230923153910.png]]

- Es un servidor o host de seguridad especialmente configurado y protegido que se coloca en la frontera de una red privada o protegida para proporcionar un punto de entrada seguro desde redes no confiables, como Internet. Su principal función es actuar como una barrera defensiva entre la red interna y el mundo exterior, permitiendo un acceso controlado y seguro a los recursos internos
![[Pasted image 20230923154140.png]]

## Private link & Private Endpoint

![[Pasted image 20230923155423.png]]

- #### Private link:
	- Servicio que permite a las redes virtuales en Azure acceder a múltiples servicios de Azure a través de una conexión privada compartida.
	- Private Link es un servicio que permite a los clientes acceder a servicios de Azure (por ejemplo, Azure SQL Database, Azure Storage, Azure App Service) a través de una conexión privada desde su red virtual en Azure. Esto significa que los recursos de Azure son accesibles directamente desde la red virtual del cliente, utilizando una conexión privada y segura, sin pasar por Internet público.
- #### Private endpoint: 
	- Punto de conexión privada dedicado para un servicio específico en Azure, lo que proporciona un mayor nivel de aislamiento y control para ese servicio en particular.

## DNS
![[Pasted image 20230923162419.png]]

![[Pasted image 20230923162427.png]]

- ### Azure DNS:
	- Es un servicio de administración de dominios de Internet que permite a los usuarios registrar y administrar nombres de dominio de Internet (por ejemplo, ejemplo.com) directamente en Azure. Esto simplifica la administración de registros DNS públicos y permite a los usuarios hospedar sus sitios web y aplicaciones en Azure con facilidad.
- ### Private DNS Zone:
	- Es un servicio que permite a las redes virtuales en Azure tener su propia zona DNS privada para la resolución de nombres internos. En lugar de utilizar servidores DNS públicos para resolver nombres, las redes virtuales pueden utilizar sus propias zonas DNS privadas para nombres internos, lo que proporciona un mayor control y aislamiento.
- ![[Pasted image 20230923162624.png]]
- // Hub - spoke -> "estrella"

## Firewall and WAF

- ### Firewall
	- Un firewall es un dispositivo o programa de software diseñado para controlar y gestionar el tráfico de red entre una red privada o segura y una red no confiable, como Internet. Su función principal es actuar como una barrera de seguridad que decide qué tráfico se permite o se bloquea según ciertas reglas y políticas de seguridad. 
	
	- ![[Pasted image 20230923175340.png]]
- ### WAF
	- Un WAF es una solución específica de seguridad cibernética diseñada para proteger aplicaciones web contra amenazas y ataques dirigidos a nivel de aplicación. A diferencia de un firewall tradicional, que se centra en el tráfico de red en general, un WAF está diseñado específicamente para proteger aplicaciones web. 
	
	- ![[Pasted image 20230923175407.png]]
	- ![[Pasted image 20230923175451.png]]
- ![[Pasted image 20230923175553.png]]
## CDN 
- Es una infraestructura de red distribuida geográficamente que se utiliza para acelerar la entrega de contenido digital, como imágenes, videos, archivos HTML y otros recursos web, a los usuarios finales. Su principal objetivo es mejorar la velocidad de carga de sitios web y aplicaciones, reducir la latencia y mejorar la experiencia del usuario al distribuir el contenido de manera eficiente y cercana a los usuarios.
- ![[Pasted image 20230923181402.png]]