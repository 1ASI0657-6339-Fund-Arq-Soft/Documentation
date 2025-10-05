# Capítulo V: Product Implementation, Validation & Deployment
## 5.1 Testing Suites & General Patterns
### 5.1.1 Backend Application Core Testing Suite 
### 5.1.2 Pattern Based Backend Application(s)

El modelo de Backend Application Core Testing Suite representa un componente esencial en la garantía de calidad del software dentro de SeniorHub, pues asegura la confiabilidad y consistencia de las funcionalidades críticas de la aplicación. En lugar de validar manualmente cada módulo de manera aislada, este conjunto de pruebas se ejecuta de forma automatizada, permitiendo detectar fallos rápidamente y garantizando que las nuevas funcionalidades no rompan comportamientos previos.

En nuestro desarrollo, hemos decidido implementar un enfoque híbrido de pruebas que combina:

- Pruebas unitarias con JUnit y Mockito, destinadas a validar el correcto funcionamiento de métodos y clases individuales, asegurando que los cálculos, validaciones y lógicas de negocio cumplan con lo esperado.
- Pruebas de integración con Selenium y Postman, enfocadas en comprobar la interacción entre microservicios clave (Notificaciones, Citas, Pagos, Gestión de Residentes), así como la correcta exposición y consumo de servicios REST.

El Backend Application Core Testing Suite se encarga también de generar reportes de cobertura de pruebas, los cuales evidencian qué porcentaje del código ha sido verificado, permitiendo a nuestro equipo priorizar módulos sensibles como la autenticación, la gestión de usuarios y las transacciones de pago.

Como parte de este proceso, hemos documentado evidencias mediante:

- Capturas de ejecución de los tests automatizados.
- Reportes de cobertura generados en el pipeline de CI/CD.
- Registros de errores y su posterior resolución.

De esta manera, la implementación del Testing Suite no solo respalda la calidad técnica del producto, sino que también fortalece la confianza del cliente en el despliegue continuo de nuevas funcionalidades bajo un entorno seguro y estable.

### 5.1.3 Pattern Based Custom Software Library

En el desarrollo de SeniorHub, se ha diseñado una biblioteca de software personalizada basada en patrones ampliamente adoptados en la industria, con el fin de garantizar modularidad, escalabilidad y facilidad de mantenimiento en el backend. Esta librería integra prácticas y patrones clave, entre los que destacan:

**- Dependency Injection (Inyección de Dependencias):**
  
A través de las capacidades que ofrece Spring Framework, se implementa de manera extensiva la técnica de inversión de control (IoC) mediante anotaciones como @Autowired y @Bean. Esto permite delegar la creación y gestión de objetos al contenedor de Spring, eliminando la necesidad de instanciaciones manuales. El resultado es una arquitectura más desacoplada, flexible y alineada con las buenas prácticas de diseño de software.

**- Entity Field (Patrón de Entidad):**
  
El uso de JPA (Java Persistence API) permite mapear entidades de dominio como objetos persistentes en la base de datos relacional. Las clases anotadas con @Entity representan tablas, mientras que sus atributos corresponden a columnas, garantizando la consistencia entre el modelo de negocio y el modelo de persistencia. Este patrón asegura que el estado de las entidades sea gestionado de forma eficiente, facilitando las operaciones CRUD y el control de transacciones.

**- Foreign Key Mapping (Mapeo de Claves Foráneas):**
  
Se implementa el patrón de relaciones entre entidades mediante anotaciones como @ManyToOne, @OneToMany y @JoinColumn. De esta forma, se establece la navegación y persistencia de asociaciones entre entidades relacionadas, como Usuario → Notificación o Residente → Cita Médica. Este mapeo refuerza la integridad referencial de la base de datos y permite a los desarrolladores trabajar con relaciones de objetos de manera natural dentro del código.

En conjunto, estos patrones constituyen la base de una Custom Software Library reutilizable y adaptable a los distintos microservicios de SeniorHub. Su diseño promueve una arquitectura más robusta, minimizando la duplicación de código y facilitando la evolución del sistema en futuras iteraciones de desarrollo.

### 5.1.4 Framework Pattern Driven Refactoring Report

Este informe documenta el proceso de refactorización de la aplicación SeniorHub, centrado en la aplicación de patrones de diseño y el uso de frameworks que facilitan la transición hacia una arquitectura moderna y escalable.

**Objetivos de la Refactorización**

- Dividir la aplicación inicial en microservicios independientes y escalables.
- Mejorar la modularidad, mantenibilidad y escalabilidad del sistema.
- Reducir la complejidad y el acoplamiento entre los componentes.
- Garantizar la consistencia y robustez mediante la adopción de patrones de diseño y frameworks adecuados.

**Contexto Actual**

La aplicación SeniorHub está diseñada como una plataforma para la gestión del bienestar de los adultos mayores en centros de cuidado, ofreciendo módulos como:

- Gestión de residentes y expedientes médicos.
- Administración de citas y recordatorios.
- Gestión de notificaciones y alertas a familiares.
- Módulo de reportes y analítica para el personal médico y administrativo.

Inicialmente, el sistema fue concebido bajo una estructura monolítica. Sin embargo, para garantizar la escalabilidad futura y una mejor separación de responsabilidades, se ha decidido migrar hacia una arquitectura basada en microservicios.

**Patrones de Diseño Seleccionados**

- Decompose by Subdomain: Descomposición del sistema según los subdominios identificados: Resident Care, Appointment Management, Notifications, User Management, Payments.
- Microservices Architecture Pattern: Implementación de microservicios especializados e independientes, cada uno con su propia lógica de negocio.
- Gateway Pattern: Uso de un punto central de entrada para enrutar solicitudes hacia los microservicios correspondientes.
- API Gateway Pattern: Abstracción de la complejidad de la arquitectura y provisión de una única interfaz para clientes y frontend.

**Frameworks Utilizados**

- Spring Boot: Framework principal para la creación de microservicios, con soporte para inyección de dependencias y rápida configuración.
- Spring Cloud: Para implementar patrones como descubrimiento de servicios, tolerancia a fallos y configuración centralizada.
- Spring Data JPA: Para la gestión de persistencia de datos de manera uniforme en cada microservicio.

**Proceso de Refactorización**

1) Análisis y Descomposición:

- Se identificaron los distintos subdominios del sistema.
- Se definió la granularidad de los microservicios.

2) Implementación de Microservicios:

- Creación de microservicios independientes en Spring Boot.
- Separación de modelos, controladores, servicios y repositorios para cada dominio.

3) Integración y Pruebas:

- Ejecución de pruebas unitarias con JUnit.
- Validación de flujos de integración entre microservicios usando Postman y Selenium.

4) Despliegue y Monitorización (en progreso):

- Contenerización de microservicios mediante Docker.
- Configuración planificada en Kubernetes para la orquestación y escalabilidad.

## 5.2 Software Configuration Management
### 5.2.1 Software Development Environment Configuration

En el desarrollo de SeniorHub, se utilizó un conjunto de herramientas y plataformas que facilitaron la organización, diseño, desarrollo, despliegue y documentación del proyecto, garantizando la colaboración efectiva y la calidad del producto.

**Project Management**

- Trello: Se empleó para la gestión ágil del proyecto, organizando tareas mediante tableros, listas y tarjetas. Permitió hacer seguimiento de los requisitos, historias de usuario y funcionalidades desarrolladas en cada sprint.

**UI/UX Design**

- Figma: Utilizado para la creación de interfaces y prototipos de experiencia de usuario, facilitando la colaboración en tiempo real entre los miembros del equipo.
- Miro: Herramienta de pizarra digital empleada para sesiones de ideación, esquemas de navegación y definición de wireframes de la aplicación.

**Software Development**

- Visual Studio Code (VS Code): Editor de código utilizado principalmente para el desarrollo frontend y la configuración de microservicios secundarios.
- IntelliJ IDEA: IDE utilizado para el desarrollo backend en Java con Spring Boot, proporcionando asistencia de código, refactorización y gestión de dependencias.
- Lenguajes y Frameworks:
  - Java 17 con Spring Boot 3.x para la implementación del backend y microservicios.
  - Node.js 18 y Vue.js para el desarrollo del frontend.
- Base de datos MySQL:
  - Configuración en puerto 3306.
  - Usuario: root.
  - Conexión gestionada a través de Spring Data JPA.
- Contenedores:
  - Uso de Docker y Docker Compose para la contenerización de los microservicios y base de datos, permitiendo replicar entornos de desarrollo y facilitar el despliegue en entornos productivos.

**Software Deployment**

- Vercel: Plataforma utilizada para el despliegue del frontend, brindando un entorno optimizado, integración continua y actualizaciones rápidas de la aplicación web.
- Docker (Backend): Planificado para el despliegue de los microservicios, garantizando portabilidad y escalabilidad.

**Documentation**
  
- GitHub: Repositorio principal donde se gestionó el control de versiones y se almacenó la documentación del proyecto, incluyendo manuales técnicos, guía de instalación y reportes de avance.

**Communication**

- Discord: Utilizado como canal de comunicación principal para coordinación en tiempo real del equipo.
- WhatsApp: Complemento para actualizaciones rápidas y comunicación fuera de reuniones.

### 5.2.2  Source Code Management

Para la gestión del código fuente del proyecto SeniorHub, se utilizó Git como sistema de control de versiones junto con GitHub como plataforma de trabajo colaborativo. Esto permitió mantener un control ordenado de los cambios, integrar de manera continua las funcionalidades desarrolladas y llevar un seguimiento claro de la documentación por capítulos.

Enlace de la organización en GitHub: [https://github.com/1ASI0657-6339-Fund-Arq-Soft](https://github.com/1ASI0657-6339-Fund-Arq-Soft)

A diferencia de un flujo tradicional de ramas como GitFlow, nuestro equipo organizó el trabajo de acuerdo con los capítulos del documento del proyecto, de tal manera que cada capítulo tenía su propia rama y su propia documentación asociada. Esto nos permitió trabajar en paralelo de forma estructurada y facilitar las revisiones de cada sección.

**Estructura de ramas**

- main: Contiene la versión final e integrada del proyecto, incluyendo documentación y código.
- chapter/*: Ramas dedicadas a cada capítulo del documento. Por ejemplo, chapter-III-architecture o chapter-V-implementation. Estas ramas se integran en main una vez completadas y validadas.
- feature/*: Se utilizaron para añadir funcionalidades específicas en el backend o frontend, relacionadas a los microservicios o al soporte del documento.
- fix/*: Usadas para corregir errores encontrados tanto en el código como en la documentación.

**Convenciones de commits**

Para mantener un historial claro y ordenado, se utilizaron commits semánticos, principalmente con los prefijos:

- feat: Para la incorporación de una nueva sección en la documentación (por ejemplo, feat: agregar 5.2.2 Source Code Management) o para nuevas funcionalidades en código.
- fix: Para corregir errores detectados en capítulos, redacción, o fallos en el código (por ejemplo, fix: corregir diagrama de microservicios en 4.1.2).

**Flujo de trabajo**

- Se crea una rama específica para un capítulo o funcionalidad (chapter-IV-design o feature-auth-service).
- Se realizan los commits siguiendo la convención feat/ o fix/, según corresponda.
- Al finalizar, se genera un Pull Request para revisión y comentarios.
- Tras ser aprobado, el capítulo o funcionalidad se integra en la rama main.

Este enfoque permitió mantener la documentación académica y el código en un solo repositorio, alineando el desarrollo de software con el progreso del documento final del proyecto.

### 5.2.3 Source Code Style Guide & Conventions
### 5.2.4  Software Deployment Configuration
## 5.3 Microservices Implementation
### 5.2.1  Sprint 1
#### 5.2.1.1     Sprint Backlog 1
#### 5.2.1.2     Development Evidence for Sprint Review
#### 5.2.1.3     Testing Suite Evidence for Sprint Review
#### 5.2.1.4     Execution Evidence for Sprint Review
#### 5.2.1.5     Microservices Documentation Evidence for Sprint Review
#### 5.2.1.6     Software Deployment Evidence for Sprint Review
#### 5.2.1.7     Team Collaboration Insights during Sprint
#### 5.2.1.8     Kanban Board --> TP1





