## Vulnerabilidades en código

- ### .ENV
	- Hay que guardar las variables que no queremos que se sepan en un archivo .env, además, este archivo con variables de entorno debe estar dentro de .gitignore
	- ![[Pasted image 20231104161952.png]]
- ### Wildcard imports 
	- Se debe importar solo lo necesario para evitar importar librerías con vulnerabilidades
	- ![[Pasted image 20231104162214.png]]
- ### Context manager
	- Se debe evitar el try catch para abrir archivos
	- ![[Pasted image 20231104162325.png]]
- ### Querys directas
	- Se debe evitar hacer querys con instrucciones directas desde el backend, la solución es ocupar SqlAlchemy
	- ![[Pasted image 20231104162441.png]]
## Sql Injection 
- Es un método de infiltración de código intruso que se vale de una vulnerabilidad informática presente en una aplicación en el nivel de validación de las entradas para realizar operaciones sobre una base de datos.​
- ![[Pasted image 20231105120045.png]]
- ![[Pasted image 20231105120101.png]]
## Cross Site Scripting (XSS) 
- Vulnerabilidad informática o agujero de seguridad típico de las aplicaciones Web, que puede permitir a una tercera persona inyectar en páginas web visitadas por el usuario código JavaScript o en otro lenguaje similar.​
## DoS
- Es un ataque a un sistema de computadoras o red que causa que un servicio o recurso sea inaccesible a los usuarios legítimos
## Modelo STRIDE
- S (Suplantación de identidad): Suplantar la identidad de un usuario legítimo o un sistema para obtener acceso no autorizado.
- T (Manipulación): Hace referencia a la alteración no autorizada o la modificación de datos o de la funcionalidad de un sistema.
- R (Repudio): El no repudio significa un servicio que proporciona prueba de la integridad y el origen de los datos, o una autenticación determinada como genuina con un alto nivel de confianza.
- I (Divulgación de información): Exposición no autorizada de información confidencial o sensible.
- D (DoS): Intentos de hacer que un sistema o servicio no esté disponible para usuarios legítimos al inundarlo con tráfico malicioso o causando problemas técnicos.
- E (Elevación de privilegios): Implica que un atacante obtiene permisos o privilegios más altos de los que debería tener.
## Seguridad en base de datos:
- Configuración de roles
- ![[Pasted image 20231105121304.png]]
- Permisos de acceso a la base de datos
- ![[Pasted image 20231105121346.png]]
## Gestores de contraseña (para sistemas)
- Azure Key Vault, GCP Secret Manager, AWS Secret Manager
-  Para cifrar claves y pequeños secretos, como contraseñas, que utilizan claves almacenadas en módulos de seguridad de hardware (HSM).
- ![[Pasted image 20231105121857.png]]
- ![[Pasted image 20231105121910.png]]
## Herramientas de monitoreo
- ### Grafana:
	- Grafana es una **plataforma interactiva y open source de visualización de datos**. Dicha plataforma permite a los usuarios ver sus datos a través de tablas y gráficos que se unifican en un panel de control (o en varios) para facilitar la interpretación y la comprensión. Sirve para ver métricas y logs
- ### Scale Fusion:
	- Administración de dispositivos y garantiza su seguridad y cumplimiento.
## Herramientas de prevención 
- ### Veracode:
	- Es una plataforma de análisis de seguridad de aplicaciones que proporciona una serie de herramientas para detectar y analizar vulnerabilidades en el código fuente de las aplicaciones.
- ### Whitehat synapsys:
	- Encuentra vulnerabilidades en sitios web y aplicaciones de forma rápida y precisa, con la escala y la agilidad que necesita para identificar riesgos de seguridad en toda su cartera de aplicaciones.