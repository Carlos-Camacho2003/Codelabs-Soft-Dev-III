# Preguntas finales - Clean Architecture en microservicios con Spring Boot

### Carlos Camacho - 2160331

## ¿Cuál es el propósito principal de Clean Architecture en el desarrollo de software?

El propósito principal de Clean Architecture es **organizar el software de forma que sea independiente de frameworks, UI, bases de datos o cualquier infraestructura externa**, asegurando que la lógica de negocio esté aislada y sea fácilmente testeable, mantenible y escalable.

---

## ¿Qué beneficios aporta Clean Architecture a un microservicio en Spring Boot?

- **Desacoplamiento:** facilita cambiar tecnologías sin afectar la lógica de negocio.
- **Testabilidad:** la lógica central se puede probar sin dependencias externas.
- **Mantenibilidad:** cada capa tiene una responsabilidad clara.
- **Escalabilidad:** se puede escalar componentes individuales sin romper el sistema.
- **Reusabilidad:** la lógica de negocio se puede reutilizar en diferentes contextos (REST, CLI, mensajería, etc.).

---

## ¿Cuáles son las principales capas de Clean Architecture y qué responsabilidad tiene cada una?

1. **Domain (Dominio):** contiene las entidades y reglas de negocio puras.
2. **Application:** define los casos de uso (UseCases) que orquestan la lógica de negocio.
3. **Infrastructure:** implementa detalles técnicos como bases de datos, controladores, etc.
4. **Interface (o Framework/Delivery):** es la capa de entrada/salida, como controladores REST, CLI, o interfaces de usuario.

---

## ¿Por qué se recomienda desacoplar la lógica de negocio de la infraestructura en un microservicio?

Porque así se logra que la lógica de negocio:
- No dependa de detalles técnicos o frameworks.
- Sea más fácil de probar unitariamente.
- Permita cambiar tecnologías (por ejemplo, de PostgreSQL a MongoDB) sin reescribir reglas de negocio.

---

## ¿Cuál es el rol de la capa de aplicación y qué tipo de lógica debería contener?

La capa de aplicación contiene **casos de uso** (UseCases), que coordinan la ejecución de la lógica de negocio.  
Aquí se define **qué debe hacer el sistema**, orquestando entidades y delegando tareas a través de interfaces.  
No debe contener lógica de presentación ni lógica de infraestructura.

---

## ¿Qué diferencia hay entre un UseCase y un Service en Clean Architecture?

- **UseCase:** representa un caso de uso del negocio, enfocado en la lógica de aplicación.
- **Service (Spring):** suele ser un componente técnico gestionado por el framework, pero puede tener responsabilidades mezcladas.

En Clean Architecture, se prefiere usar el término **UseCase** para enfatizar que esa clase representa un comportamiento del dominio, y no un simple servicio técnico.

---

## ¿Por qué se recomienda definir Repositories como interfaces en la capa de dominio en lugar de usar directamente JpaRepository?

Para mantener el **principio de inversión de dependencias**, donde:
- La lógica de negocio **depende de abstracciones** (interfaces).
- La infraestructura **implementa esas interfaces**.

Esto evita acoplar directamente el dominio a una tecnología específica como JPA, permitiendo cambiar de motor de persistencia sin afectar la lógica central.

---

## ¿Cómo se implementa un UseCase en un microservicio con Spring Boot y qué ventajas tiene?

**Implementación:**
1. Crear una interfaz del UseCase en la capa de aplicación.
2. Implementar la lógica en una clase concreta.
3. Usar interfaces para interactuar con repositorios o servicios externos.
4. Inyectar esta clase desde el controlador (API) o consumidor de eventos.

**Ventajas:**
- Código modular, fácil de probar.
- Lógica de negocio centralizada y aislada.
- Bajo acoplamiento con infraestructura.

---

## ¿Qué problemas podrían surgir si no aplicamos Clean Architecture en un proyecto de microservicios?

- **Alto acoplamiento:** cambios en la base de datos o framework afectan toda la aplicación.
- **Difícil mantenimiento:** lógica mezclada en controladores o servicios técnicos.
- **Baja testabilidad:** pruebas costosas y lentas al no poder aislar la lógica.
- **Reusabilidad limitada:** lógica de negocio atada a detalles técnicos.

---

## ¿Cómo Clean Architecture facilita la escalabilidad y mantenibilidad en un entorno basado en microservicios?

- **Separación de responsabilidades:** cada componente tiene una función clara.
- **Facilidad para pruebas y despliegues independientes.**
- **Desacoplamiento tecnológico:** facilita migraciones tecnológicas.
- **Organización clara del código:** permite crecimiento sostenible del sistema.

---
