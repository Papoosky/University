- Machine learning es la técnica de entrenar un computador para encontrar patrones, hacer predicciones y aprender desde la experiencia sin haber sido explícitamente programado.
- Machine learning (ML) es una subcategoría de Inteligencia Artificial (AI) que usa algoritmos para identificar patrones, crear predicciones dentro de un set de datos. Estos datos pueden consistir en números, texto e incluso fotos.
- ## Existen 3 tipos de aprendizajes:
	- ### Aprendizaje supervisado: 
		- El modelo de se entrena con un conjunto de datos etiquetados. Los datos etiquetados son datos en los que la salida deseada ya se conoce. 
	- ### Aprendizaje no supervisado: 
		-  El modelo se entrena con un conjunto de datos no etiquetados. Los datos no etiquetados son datos en los que la salida deseada no se conoce.
	- ### Aprendizaje por refuerzo:
		- El modelo de aprendizaje automático aprende a realizar una tarea interactuando con su entorno. 
- **![](https://lh7-us.googleusercontent.com/jFeQ3Vi7Pnbjf7XtA48EZkgKhSS_oNm0SiRAgWEAf89tEtMEZSO0jkp0h4WM9WlT76uDowgaRCTy6EBj2nufjK8DFvXNtwdeoBewvifoAFrrCWfmcQJ-Tld7NSkvt65LJHoytrXtetCtoEPzkh7i-TNozw=s2048)**hjkk

- ## Machine learning
	- El aumento del rendimiento de las tecnologías informáticas existentes (ej. CPU, GPU) y la disponibilidad de dispositivos informáticos especializados (ej. TPU) han desempeñado un papel importante en el crecimiento del aprendizaje profundo.
	- La computación en la nube ofrece ventajas de flexibilidad, elasticidad y economía, que la han convertido en un modelo de computación común entre los científicos.
	- El aprendizaje automático "como servicio" puede considerarse como uno de los servicios más demandados cuando se adoptan infraestructuras informáticas a gran escala.
	- Actualmente el uso de GPU y TPU a través del Cloud tiene un mayor impacto para las tareas de ML.
	- ### Cloud TPU: 
		- Los TPU son ASIC desarrollados a medida por Google y que se utilizan para acelerar las aplicaciones de aprendizaje automático.
		- Cloud TPU le permite ejecutar sus cargas de trabajo de aprendizaje automático en hardware de TPU mediante TensorFlow. Está diseñado para ofrecer el <mark style="background: #FF5582A6;">máximo rendimiento y flexibilidad</mark> para ayudar a investigadores, desarrolladores y propietarios de empresas a crear sus aplicaciones de aprendizaje automático en TPU.
		- ![[Pasted image 20231029220755.png]]
	- ### Ciclo de aprendizaje de una aplicación de machine learning
		- **![](https://lh7-us.googleusercontent.com/TXwSBh-bEwFDiV6Tw2FSt_nE9sSYRt-xWFmZUKRhnQVMVaqU8DdioXaD2CUkzBHSzjTPJ4hR_0FwGLA7DR5PeuJX1CYmoytJBVDlXMJeWz3u892QG6eRI2pFo8oBByoC8hUTSu2ItpKRZKm03EwQYb8CGA=s2048)**
	- ### Distintos roles en arquitectura de machine learning
		- **![](https://lh7-us.googleusercontent.com/AOs1yn58EgTzlK4L7sflz6eHYNWpIh33RpoIrnEYufH6wnHQK5KGeX3GwZ65vRYNq-qCDPNFMRSwc9_yJO-nia6U03cIdTVmm15Y6gCJklMMgvQuNTHhFnmN8GP_6InYK7psPtb0idcyZsyP_UJpbJtPEQ=s2048)**
	- **![](https://lh7-us.googleusercontent.com/M0kpscoJQw5zm-yhLzR_SFwGQKp9QE7BQgTHkZLzoDe-T-IvD41Rl0RqZXQp3nCyBpQU-9QRyeMyOCdjTC-GzPZBAeqxxTMCi-sQ9zAUDUYUN3ECnrYuBGubE_YzfIE-7CgyrZLln19EMgYLymrjyYCehA=s2048)**

- ## Arquitectura basada en eventos
	- La arquitectura basada en eventos es un modelo y una arquitectura de software que sirve para diseñar aplicaciones. En un sistema como este, el registro, la comunicación, el procesamiento y la permanencia de los eventos son la estructura central de la solución. Esto difiere del modelo tradicional basado en solicitudes.
	- ### Ventajas: 
		- Desacoplamiento: Los componentes no necesitan conocerse entre sí.
		- Escalabilidad: Se pueden escalar componentes individualmente dependiendo de la carga de trabajo.
	- ### Desventajas: 
		- Complejidad
		- Latencia
	- **![](https://lh7-us.googleusercontent.com/JQ3QbsfZ-WwU3PCAV_gV_psMdio5M9LowzjhLiamrHFdOMtCZRKc4ExPNm-BC8GfyBl2WhPUv6N5Zsd9l21Cjbaj7dlhUtwT9QHVS7yRk33fVb6PRLAciudkfgQDBuxRNAU5Az7i4FWwCPcnJKifJgiZoA=s2048)**
	- Los microservicios basados en eventos (event-driven microservices) se encuentran de forma emergente, donde cada microservicio es autocontenido y desacoplado, es decir puede ejecutar distintas tecnologías y sin conocimiento de los servicios que lo utilizarán.
	- La comunicación ocurre de forma asincrónica a través de un sistema de mensajes. Principalmente se habla de Productores y Consumidores.
	- Apache Kafka es uno de los estándares como core de sistema para ser usado basado en eventos.
	- ### Apache kafka:
		- Apache Kafka es una plataforma distribuida para la transmisión de datos que permite no solo publicar, almacenar y procesar flujos de eventos de forma inmediata, sino también suscribirse a ellos. Está diseñada para administrar los flujos de datos de varias fuentes y enviarlos a distintos usuarios.
		- **![](https://lh7-us.googleusercontent.com/c0FZqrl5Sscjsgrm5vRkcYxFW0t0M0ZPktq_AWrtIT6hyrX9Gd5h8rshbfWH2Ir6i5KY4C7MAU0Uz_mlbEw-Yg7pe4dKu48vniRZiEh_umvObTzEVzz_NNc9VGMQQGLsQGfDYkdz0CovKY4F1TQTwl7oeA=s2048)**
	- **![](https://lh7-us.googleusercontent.com/ccDR1a9o9fePijVcWOGZSnXn36IspumZLDW0iUsjZz8BvE2kckPTHxD9D0IwSgSBRIia2GG-1_WMth85ehGVq5oqvkK3VklkUAH6rZPeVTSZ3Ojmo5Qy_YRVme1RkBjDbzD-w1IKUyduOW2IlNCelIT7VQ=s2048)**
	- **![](https://lh7-us.googleusercontent.com/JztEyhCw5dCR2L574bUsu2vjFm3MjCCqhuYy2PrB0wYq6TlTRc1TGTxLHChQhgiw7QeDcHV0i-otVDlRID6tHfQ4DWA-ft540dsNdj_r-Q2hq1Dkmwpx5ga0uqq6Ws3aFCnYNB6oiLMfgPdwyriqqUoWfA=s2048)**
	- Los eventos llegan a Azure Event Hubs.
	- Se activa una aplicación de funciones para controlar el evento.
	- El evento se almacena en una base de datos de Azure Cosmos DB.
	- Si la aplicación de funciones no puede almacenar el evento correctamente, el evento se guarda en una cola de almacenamiento para procesarlo más adelante.
