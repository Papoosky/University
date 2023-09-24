
## Aplicaciones tradicionales y aplicaciones nativas de nube


- ### Aplicaciones tradicionales:
	- Las aplicaciones tradicionales suelen tener una arquitectura monolítica, en la que todos los componentes y funciones de la aplicación están agrupados en un solo conjunto de código.
	- Estas aplicaciones a menudo se ejecutan en servidores físicos o máquinas virtuales que se administran de manera centralizada en un centro de datos local o en servidores alojados en la nube.
	- El desarrollo de aplicaciones tradicionales tiende a tener ciclos de desarrollo más largos y menos frecuentes, lo que puede hacer que la implementación de nuevas características y actualizaciones sea más lenta.
	- La escalabilidad se logra generalmente aumentando la capacidad de los servidores individuales, lo que puede ser costoso y limitado en términos de escalabilidad.
- ### Aplicaciones nativas de nube:
	- Las aplicaciones nativas de la nube se crean desde cero y están optimizadas para la escala y el rendimiento de la nube. Se basan en arquitecturas de microservicios, utilizan servicios administrados y se benefician de la entrega continua para conseguir confiabilidad y una comercialización más rápida.
	- El desarrollo de aplicaciones nativas de nube tiende a seguir prácticas ágiles y DevOps, lo que permite ciclos de desarrollo más cortos y una implementación continua rápida.
	- La escalabilidad se logra aumentando el número de instancias de servicios individuales, lo que permite una escalabilidad horizontal más efectiva y rentable.
	- Estas aplicaciones están diseñadas para ser independientes de la infraestructura subyacente y pueden ejecutarse en múltiples entornos de nube o en entornos locales con facilidad.
- ![[Pasted image 20230920200545.png]]

## DevOps
- El término "DevOps" surge de la unión de las palabras "development" (desarrollo) y "operations" (operaciones), pero representa un conjunto de ideas y prácticas que van más allá de la combinación de ambos conceptos. DevOps incluye sistemas de seguridad, maneras de trabajar en colaboración, análisis de datos, entre otras características.
- ![[Pasted image 20230920201804.png]]
- DevOps es un enfoque cultural y práctico para el desarrollo de software y la administración de infraestructura que tiene como objetivo mejorar la colaboración y la eficiencia entre los equipos de desarrollo (Dev) y operaciones (Ops) en una organización.
- **Entrega Continua**
- **Automatización**
- **Monitorización y Retroalimentación**
- **Mejora Continua**
1. **Plan (Planificar):** En esta etapa, se definen los objetivos del proyecto, se planifican las tareas y se establecen las métricas de éxito. También se determina la arquitectura y la infraestructura necesarias para la aplicación. **Ejemplo:** Imagina que estás desarrollando una aplicación de comercio electrónico. En la fase de planificación, decides que el objetivo del proyecto es aumentar las ventas en línea en un 20% en los próximos seis meses. Planificas las características que se agregarán, como un carrito de compras mejorado y un proceso de pago más rápido.
2. **Continuous Feedback (Retroalimentación Continua):** Durante todo el proceso de desarrollo y operación, se recopila retroalimentación y se realiza un seguimiento de métricas clave. Esta información se utiliza para mejorar continuamente la aplicación y los procesos.
3. **Operate (Operar):** En esta etapa, se monitorea y opera la aplicación en producción. Se gestionan las configuraciones, se aplican parches y se realizan tareas de mantenimiento para garantizar que la aplicación funcione sin problemas.
4. **Deploy (Despliegue):** En esta etapa, se implementa la aplicación en un entorno de prueba o producción. El despliegue puede ser manual o automatizado, y se asegura de que la aplicación esté disponible para su uso.
5. **Continuous Integration (Integración Continua):** En esta etapa, los desarrolladores combinan su código en un repositorio compartido de manera frecuente (varias veces al día). Se ejecutan pruebas automáticas para detectar errores tempranamente y garantizar que el código sea estable.
6. **Build (Construcción):** En esta etapa, se compila el código fuente y se generan los artefactos de software (por ejemplo, archivos binarios) que serán desplegados en los servidores de producción.

- **¿Porqué son necesarias las aplicaciones nativas en Cloud?**
	- **Escalabilidad**
	- **Eficiencia de Costos**
	- **Agilidad Empresarial**
	- **Disponibilidad y Tolerancia a Fallos**

- **¿Cuál es la importancia de los contenedores?**
	- **Portabilidad**
	- **Consistencia:** Los contenedores garantizan que una aplicación se ejecute de la misma manera en cualquier lugar.
	- **Eficiencia de Recursos**
	- **Despliegue Rápido**

- **Referente al concepto de DevOps, ¿qué lo llevó a su creación?**
	- Se debió a una serie de desafíos y problemas que surgieron en la industria de la tecnología de la información a medida que las organizaciones adoptaban prácticas de desarrollo de software más ágiles y buscaban acelerar la entrega de aplicaciones.
	- Los equipos de desarrollo y operaciones funcionaban de manera aislada, con objetivos y métricas diferentes. Esto llevaba a una falta de colaboración y entendimiento mutuo, lo que a su vez causaba problemas en la entrega de software.
