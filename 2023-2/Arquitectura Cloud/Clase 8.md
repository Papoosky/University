Las empresas requieren análisis de datos y generar estadísticas prácticas a partir de ellos.

## Ciclo de vida de los datos
- Transferencia (servicios como Pub/Sub, Transfer Appliance, Big Query)
- Almacenamiento (servicios como Cloud Storage, Bigtable, Memorystore)
- Procesamiento y transformación ( Dataflow, Dataproc, Dataprep, BigQuery)
- Análisis (BigQuery)
- Visualización (Looker Studio, Looker)
## Etapas que se ejecutan durante todo el ciclo de vida de los datos:
- Integración de datos (Data fusion)
- Administración de metadatos (Data Catalog)
- Administración de flujos de trabajo (Cloud Composer)
![[Pasted image 20231022201023.png]]

## Captura
- En esta etapa se recopilan los datos desde distintas fuentes como base de datos, archivos, sensores y redes sociales
	- ### Herramientas:
		- #### Cloud pub/sub: 
			- Servicio de mensajería escalable y duradero que permite la comunicación asíncrona entre aplicaciones. Está diseñado para facilitar la creación de sistemas distribuidos y aplicaciones en la nube que necesitan enviar y recibir mensajes entre componentes de manera confiable y escalable.
		- #### Data transfer service: 
			- Conjunto de servicios y soluciones que permiten la transferencia de datos desde una aplicación SaaS , generalmente de manera eficiente y segura.
		- #### Storage transfer service: 
			- Transferir datos de un origen a un destino en la nube o desde on-prem, lo que facilita la migración de datos y la sincronización de datos entre diferentes servicios de almacenamiento en la nube.
		- #### Cloud IoT core:
			- Diseñado para gestionar y conectar dispositivos IoT (Internet de las cosas) a la plataforma de Google Cloud. Proporciona una solución escalable, segura y completamente administrada para la administración de dispositivos IoT y la gestión de datos generados por estos dispositivos.
- ## Process
	- En esta etapa se limpian, transforman y preparan los datos para el análisis.
	- ### Herramientas:
		- #### Cloud dataflow:
			- Servicio de procesamiento de datos en tiempo real y por lotes en la plataforma de Google Cloud. Está diseñado para ayudar a las organizaciones a procesar, transformar y analizar grandes volúmenes de datos de manera eficiente y escalable.
		- #### Cloud dataproc: 
			- Permite a las organizaciones ejecutar clústeres de procesamiento de datos de código abierto de manera eficiente y escalable en la nube. Está diseñado para procesar grandes volúmenes de datos y realizar análisis de datos, procesamiento de lotes, procesamiento en tiempo real y tareas similares.
		- #### Cloud dataprep: 
			- Diseñado para la preparación y limpieza de datos de manera eficiente y escalable. Está destinado a ayudar a las organizaciones a abordar el desafío de transformar y preparar datos desordenados en formatos más limpios y estructurados, lo que facilita su análisis y utilización en aplicaciones y sistemas.
- ## Store (data lake and data warehousing)
	- ### Herramientas: 
		- #### Cloud storage: 
			- Permite almacenar y recuperar datos de manera segura, escalable y duradera. Se puede usar como data lake para data estructurada y no estructurada.
		- #### Bigquery storage: 
			- Es un servicio de análisis de datos totalmente administrado que permite realizar consultas SQL en datos masivos a gran velocidad. El "BigQuery Storage" se refiere a la forma en que BigQuery almacena y administra sus datos internamente
- ## Análisis: 
	- En esta etapa se utilizan técnicas estadísticas, de aprendizaje automático y de inteligencia artificial para extraer información de los datos.
	- ### Herramientas:
		- #### BigQuery
- ## Ejemplos: 
- 1. Canalización de datos que integra grandes cantidades de datos de múltiples orígenes en una plataforma de análisis unificada en Azure.
- https://learn.microsoft.com/en-us/azure/architecture/example-scenario/data/data-warehouse
	- ![[Pasted image 20231027131748.png]]
	- La orquestación es el proceso de coordinar los diferentes componentes de una arquitectura. En este caso, la orquestación se realiza mediante Azure Data Factory, que es un servicio de integración de datos que automatiza la recopilación, transformación y carga de datos.
	- 
- 2. Esta carga de trabajo de ejemplo muestra varias formas en que las pequeñas empresas (PYMES) pueden modernizar los almacenes de datos heredados y explorar herramientas y capacidades de big data, sin extender demasiado los presupuestos y las habilidades actuales.
- https://learn.microsoft.com/en-us/azure/architecture/example-scenario/data/small-medium-data-warehouse
	- ![[Pasted image 20231027131949.png]]