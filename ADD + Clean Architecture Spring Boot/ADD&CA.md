# Preguntas sobre Attribute-Driven Design (ADD) y Clean Architecture

### Carlos Camacho - 2160331

## ¿Qué es Attribute-Driven Design (ADD) y cuál es su propósito en el diseño de software?

**Attribute-Driven Design (ADD)** es una metodología de diseño arquitectónico centrada en los *atributos de calidad* del sistema, como rendimiento, seguridad, disponibilidad, entre otros.  
Su propósito es guiar la definición de la arquitectura basándose en los requisitos no funcionales y restricciones tecnológicas, asegurando que el sistema cumpla con los niveles esperados de calidad.

---

## ¿Cómo se relaciona ADD con Clean Architecture en el proceso de diseño de sistemas?

ADD se enfoca en **definir la arquitectura** desde una perspectiva de calidad, mientras que **Clean Architecture** se encarga de **estructurar el código** en capas desacopladas y con responsabilidades bien definidas.  
Ambos enfoques se complementan: ADD define *qué* debe lograrse (en términos de calidad), y Clean Architecture define *cómo* implementarlo de manera mantenible y flexible.

---

## ¿Cuáles son los pasos principales del método ADD para definir una arquitectura de software?

1. Identificar requisitos del sistema.
2. Definir atributos de calidad prioritarios.
3. Establecer restricciones tecnológicas.
4. Seleccionar tácticas arquitectónicas para satisfacer los atributos de calidad.
5. Definir los módulos principales del sistema.
6. Especificar la interacción entre componentes.

---

## ¿Cómo se identifican los atributos de calidad en ADD y por qué son importantes?

Los atributos de calidad se identifican a partir de los **requisitos no funcionales** y las **expectativas del negocio**.  
Ejemplos comunes incluyen:
- **Rendimiento:** tiempo de respuesta inferior a 2 segundos.
- **Disponibilidad:** 99.9% de uptime.
- **Seguridad:** cifrado de datos sensibles.

Estos atributos son clave porque guían las decisiones arquitectónicas y tácticas necesarias para cumplir con los objetivos del sistema.

---

## ¿Por qué Clean Architecture complementa ADD en la implementación de una solución?

Porque **separa la lógica de negocio de las dependencias tecnológicas**, lo cual permite:
- Implementar las tácticas definidas en ADD sin acoplarlas a frameworks.
- Cambiar tecnologías (bases de datos, servicios externos) sin afectar la lógica de negocio.
- Facilitar pruebas, mantenimiento y escalabilidad del sistema.

---

## ¿Qué criterios se deben considerar al definir las capas en Clean Architecture dentro de un proceso ADD?

- **Dominio:** entidades y lógica de negocio pura, sin dependencias externas.
- **Aplicación:** casos de uso que coordinan la lógica.
- **Infraestructura:** implementación concreta (bases de datos, APIs externas).
- **Presentación:** interfaz de usuario o capa de API.

Las **dependencias deben ir hacia adentro**, aplicando inversión de dependencias para desacoplar la lógica central de detalles tecnológicos.

---

## ¿Cómo ADD ayuda a tomar decisiones arquitectónicas basadas en necesidades del negocio?

ADD traduce los **objetivos del negocio** (como alta disponibilidad o bajo tiempo de respuesta) en **tácticas arquitectónicas** concretas.  
Por ejemplo:
- Si el negocio necesita alta disponibilidad → se diseñan componentes replicados con failover automático.
- Si requiere bajo tiempo de respuesta → se usa caching y consultas optimizadas.

---

## ¿Cuáles son los beneficios de combinar ADD con Clean Architecture en un sistema basado en microservicios?

- Diseño centrado en atributos de calidad.
- Separación clara de responsabilidades.
- Escalabilidad y mantenibilidad.
- Independencia tecnológica y desacoplamiento.
- Facilidad para pruebas, evolución y adaptación.
- Arquitectura robusta y alineada con objetivos del negocio.

---

## ¿Cómo se asegura que la arquitectura resultante cumpla con los atributos de calidad definidos en ADD?

- Realizando **pruebas de rendimiento, carga y seguridad**.
- Evaluando métricas clave (latencia, disponibilidad, etc.).
- Aplicando **revisiones arquitectónicas periódicas**.
- Optimizando tácticas si se detectan desviaciones (por ejemplo, mejorando consultas o usando balanceo de carga).

---

## ¿Qué herramientas o metodologías pueden ayudar a validar una arquitectura diseñada con ADD y Clean Architecture?

- **Pruebas de carga:** JMeter, k6.
- **Revisiones de arquitectura:** ATAM, ADRs.
- **Análisis estático de código:** SonarQube.
- **Monitorización:** Prometheus, Grafana.
- **Pruebas de seguridad:** OWASP ZAP.

---
