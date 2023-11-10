## Tipos de ataque por capas

![[Pasted image 20231106160442.png]]
- ### Sniffing
	- El ataque de "sniffing" se centra en la monitorización y la captura pasiva del tráfico de red. El atacante escucha el tráfico sin necesidad de intervenir directamente en la comunicación.
	- El objetivo principal del "sniffing" es la obtención de datos sensibles que se están transmitiendo a través de la red, como contraseñas, información de inicio de sesión u otros datos confidenciales.
	- El ataque de "sniffing" generalmente no implica alterar o interrumpir la comunicación; el atacante simplemente observa el tráfico y registra los datos.
	- #### Formas de prevenir: 
		- Utilizar protocolos seguros HTTPS, TLS, VPN
		- Uso de redes privadas
- ### Spoofing
	- Tipo de ataque en el que un atacante finge ser otra entidad, dispositivo o dirección de red para engañar a otros dispositivos y obtener acceso no autorizado o realizar actividades maliciosas en una red.
	- Esto implica la manipulación de la información en la capa de enlace de datos, como direcciones MAC, para engañar a otros dispositivos y hacer que confíen en la identidad falsa del atacante.
- ### MITM
	- Consiste en un atacante que se interpone entre dos partes que están comunicándose, actuando como intermediario no autorizado. El atacante intercepta y, en algunos casos, modifica la comunicación entre las partes, lo que le permite leer, alterar o inyectar datos en la transmisión. El objetivo principal de un ataque MITM es la obtención de información confidencial o la manipulación de la comunicación para beneficio propio o con fines maliciosos.
- ### Hijacking
	- Ataques informáticos que involucran la toma de control de una sesión de comunicación o interacción entre un usuario y un sistema o servicio en línea. Estos ataques pueden permitir a un atacante tomar el control de una sesión legítima y actuar en nombre del usuario, lo que puede llevar a actividades maliciosas, como robo de información, suplantación de identidad o manipulación de datos.
	- Session Hijacking: En un ataque de secuestro de sesión, un atacante intercepta o roba la identificación de sesión de un usuario legítimo y la utiliza para acceder a una cuenta o sesión en un servicio en línea.
	- DNS Hijacking: En un ataque de secuestro de DNS, un atacante redirige las solicitudes de nombres de dominio a servidores DNS maliciosos. Esto puede hacer que los usuarios sean dirigidos a sitios web falsos o peligrosos.
	- Clickjacking: El clickjacking es un tipo de ataque en el que un atacante superpone una página web maliciosa sobre una página web legítima y engaña a los usuarios para que hagan clic en elementos ocultos o acciones no deseadas sin darse cuenta.
- ### Pishing
	- El phishing es una técnica en la que un atacante intenta engañar a las personas para que revelen información confidencial, como contraseñas, números de tarjetas de crédito o información personal, haciéndose pasar por una entidad de confianza. Este ataque suele llevarse a cabo a través de mensajes de correo electrónico, mensajes de texto, llamadas telefónicas o sitios web falsos que imitan a organizaciones legítimas.
- ### Prevención
	- Priorizar conexiones HTTPS
	- Evitar WIFI público
	- Incorporar multifactor autenticators
	- Segmentación de redes, zero trust architecture
	- Encriptar emails
- ## Zero Trust Arquitecture
	- Enfoque de seguridad de redes y sistemas que se basa en la premisa de que no se debe confiar en ningún usuario, dispositivo o entidad, ya sea dentro o fuera de una red corporativa, por defecto. En lugar de confiar en la ubicación o la red de origen de una conexión, la arquitectura de Cero Confianza asume que todo en la red es potencialmente no seguro y requiere una autenticación y autorización rigurosas antes de permitir el acceso a recursos.
	- Los usuarios y dispositivos solo deben tener acceso a los recursos necesarios para realizar sus funciones, evitando el acceso a recursos innecesarios.
- ## Security by design
1. Establecer el contexto antes de diseñar un sistema 
	- Antes de poder crear un diseño de sistema seguro, es necesario tener una buena comprensión de los fundamentos y tomar medidas para abordar cualquier deficiencia identificada.
2. Dificultar el compromiso 
	- Diseñar teniendo en cuenta la seguridad significa aplicar conceptos y utilizar técnicas que dificulten que los atacantes comprometan sus datos o sistemas.
3. Dificultad de disrupción 
	- Cuando los servicios críticos o de alto valor dependen de la tecnología para su entrega, se vuelve esencial que la tecnología esté siempre disponible. En estos casos, el porcentaje aceptable de "tiempo de inactividad" puede ser efectivamente cero.
4. Facilite la detección de compromisos
	- Incluso si toma todas las precauciones disponibles, todavía existe la posibilidad de que su sistema se vea comprometido por un ataque nuevo o desconocido. Para tener la mejor oportunidad de detectar estos ataques, debe estar bien posicionado para detectar compromisos.
5. Reducir el impacto del compromiso 
	- Diseñe para minimizar naturalmente la gravedad de cualquier compromiso.
- ### Recomendaciones
	- Priorizar el uso de lenguajes de memoria segura, c#, rust, ruby, java, go, swift
	- Incorpora características arquitectónicas que permiten una memoria detallada
	- Adquirir y mantener componentes de software bien seguros.
	- Utilice marcos de plantillas web que implementen automáticamente
		escapar de la entrada del usuario para evitar ataques web XSS
	- Utilice consultas parametrizadas en lugar de incluir la entrada del usuario en consultas, para evitar ataques de inyección SQL.
	- Utilizar herramientas para analizar el código fuente del producto y el comportamiento de las aplicaciones para detectar prácticas propensas a errores.
- ## CVE - Common Vulnerabilities and Exposures
	- Esta página muestra los componentes de la puntuación CVSS 
	- CVSS = El Sistema de puntuación de vulnerabilidad común (CVSS) proporciona una manera de capturar las características principales de una vulnerabilidad y producir una puntuación numérica que refleje su gravedad. Luego, la puntuación numérica se puede traducir en una representación cualitativa (como baja, media, alta y crítica) para ayudar a las organizaciones a evaluar y priorizar adecuadamente sus procesos de gestión de vulnerabilidades.
	- ![[Pasted image 20231106183438.png]]
- ## Shodan 
	- Página para buscar vulnerabilidades
- ## OWASP (Open Worldwide Application Security Project) 
	- Es un documento de concientización estándar para desarrolladores y seguridad de aplicaciones web. Representa un amplio consenso sobre los riesgos de seguridad más críticos para las aplicaciones web.
	- ![[Pasted image 20231106193626.png]]
- ## Broken acces control 
	- Vulnerabilidad de seguridad en aplicaciones web y sistemas que ocurre cuando las restricciones de acceso a recursos o funciones no se aplican de manera adecuada o son vulnerables a ser eludidas por usuarios no autorizados.
	- Ejemplo: URLs predecibles
	- ![[Pasted image 20231106194149.png]]