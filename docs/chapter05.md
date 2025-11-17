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

Nuestra guía de estilo y convenciones para el código fuente es esencial para asegurar la limpieza, coherencia y legibilidad en todos nuestros proyectos de desarrollo. Estas directrices permiten que los equipos colaboren de manera efectiva y que el código resultante sea mantenible a largo plazo.

**Convenciones de nomenclatura**

- Clases → PascalCase (ejemplo: UserService, LoginController).
- Variables y métodos → camelCase (ejemplo: userName, startDate, calculateTotal).
- Paquetes → lowercase.
- Constantes → UPPER_CASE con guiones bajos (ejemplo: MAX_USERS, DEFAULT_TIMEOUT).

**Indentación y espaciado**

- Se utilizan 4 espacios por nivel de indentación (no tabulaciones).
- Se mantiene espaciado consistente, incluyendo un espacio antes y después de los operadores (ejemplo: a + b en lugar de a+b).

**Comentarios y documentación**

- Los comentarios se agregan solo cuando es necesario explicar lógica compleja o dar contexto.
- Se priorizan comentarios claros, concisos y actualizados.
- Documentación adicional se mantiene en archivos por capítulo (docs/) dentro del repositorio.

**Organización del código**

- Funciones y variables se agrupan de manera lógica.
- El código muerto o comentado se elimina para mantener limpieza y eficiencia.
- Los módulos siguen una estructura coherente y alineada a las prácticas de DDD en el proyecto.

**Convenciones de commits**

Se sigue la convención de Gitflow, usando prefijos en cada commit para indicar su propósito:

- feat: nueva característica.
- fix: corrección de error.
- doc: documentación.
- refactor: refactorización sin cambios funcionales.
- test: pruebas unitarias o integrales.

**Herramientas de calidad de código**

- Se aplican herramientas de análisis estático como Checkstyle, SonarLint o ESLint según el lenguaje y contexto del módulo.
- Estas herramientas aseguran el cumplimiento automático de las convenciones y ayudan a identificar problemas potenciales de calidad.

Con estas pautas, garantizamos que nuestro código fuente sea legible, mantenible y consistente, favoreciendo la colaboración y la evolución a largo plazo del proyecto.

### 5.2.4  Software Deployment Configuration

**Landing page:**

Para el despliegue de la landing page utilizaremos el servicio de Vercel (https://vercel.com/). A continuación se presentará el proceso para realizarlo:

1.	Crear o tener una cuenta de Vercel ingresando a su página web oficial (https://vercel.com/). Esta cuenta se puede crear con Github, Gitlab o Bitbucket o con un correo convencional.
   
<div align="center">
  	<img width="200" height="250" alt="image" src="https://github.com/user-attachments/assets/7bc1e459-89d1-4201-a3d5-1732c2e242de" />
</div>

2.	Una vez con la sesión iniciado, dirigirse a la sección de sitios y seleccionar “Import Git Repositoryt”

**Codigo ya creado:**
<div align="center">
<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/146fa885-8845-4882-8652-c6b21d2306f9" />
</div>

<div align="center">
<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/a7daa246-bd7b-4ade-a619-cee5a69c3d0c" />
</div>

3.	Seleccionamos el repositorio y luego nos aparecerá el botón “Deploy Site” al final del formulario.

<div align="center">
<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/015ac12e-a379-4f53-ba58-9149d506f693" />
</div>

4.	De esta manera, la página ya estaría deployada en unos instantes. Link de deployment:[https://seniorhub.vercel.app/](https://seniorhub.vercel.app/)

<div align="center">
<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/34932c24-880b-4102-b7cd-371806f7a36f" />
</div>

## 5.3 Microservices Implementation
### 5.3.1  Sprint 1

A continuación, se presentará el sprint planning 1 donde se mostrarán las evidencias de planificación para la implementación de SeniorHub.

| Sprint # |	Sprint 1|
|----------|----------|
||Sprint Planning Background|
| Date |	1/10/2025 |
| Time |	15:00 horas (GMT -5) |
| Location |	Modalidad remota por Discord |
| Prepared By |	Fatima Asmad |
| Attendees (to planning meeting) |	Todos los miembros del equipo SeniorHub |
| Sprint n – 0 Review Summary |	El proyecto se desarrollo de manera parcial para esta enttrega , se espera hacer un avance del backend de los microservicios.|
| Sprint n – 1 Retrospective Summary	 | En este presente sprint se tiene como objetivo desarrollar tres microservicios que conecten con APIs externos: -	Servicio para subir archivos blob a la nube -	Servicio para subir imagenes y media a la nube -	API de Stripe para realizar pagos. Asimismo, vamos a conectarlos a la API inicial a través de un API Gateway facilitado por Netflix Eureka y Spring Cloud.|
||Sprint Goal & User Stories|
|Sprint 1 Velocity	|19 |
|Sum of Story Points|	14|

#### 5.2.1.1     Sprint Backlog 1

Se presenta el sprint backlog, donde hemos utilizado Trello para visualizar el progreso de las tareas.
Link de Trello: [https://trello.com/invite/b/68e547015b3e5338979e9169/ATTIb0ff9795cc89dcfecc531e9f16c08c02644A6A9F/tf1asi0657202520](https://trello.com/invite/b/68e547015b3e5338979e9169/ATTIb0ff9795cc89dcfecc531e9f16c08c02644A6A9F/tf1asi0657202520)

<div align="center">
<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/65488336-1092-402f-8568-f868a151a66a" />
</div>

| User Story |	Work Item / Task |	Id	| Title	| Description |	Estimation (Hours)|	Assigned To |	Status|
|-|-|-|-|-|-|-|-|
|US-29| Información del servicio	|	T1	|Diseño de estructura base del Landing Page	|Crear el esqueleto de la página incluyendo header, footer y secciones principales.	|6	|equipo SeniorHub |	Done |
| | |		T2	|Maquetado de contenido informativo	| Redactar y estructurar la información de los servicios ofrecidos en el landing page.|	5	| equipo SeniorHub |	Done|
|	|	|T3	| Implementación del diseño responsivo	|Adaptar el sitio para visualización correcta en diferentes dispositivos usando HTML, CSS y Bootstrap. |	6	| equipo SeniorHub |	In Process|
|	|	|T4	| Publicación en GitHub|	Subir la primera versión funcional del Landing Page al repositorio oficial.|	3	|equipo SeniorHub |	To Review|

| User Story |	Work Item / Task |	Id	| Title	| Description |	Estimation (Hours)|	Assigned To |	Status|
|-|-|-|-|-|-|-|-|
|US-30 | Formulario de contacto	|	T1|	Diseño del formulario de contacto |	Crear el formulario con los campos nombre, correo y mensaje.	|4	|equipo SeniorHub|	Done|
|	|	|T2	|Implementar validaciones básicas|	Validar formato de email y campos obligatorios antes del envío.|	3	|equipo SeniorHub|	Done|
| |	|	T3	|Conexión con endpoint simulado	| Implementar envío del formulario hacia un servicio simulado o endpoint temporal.|	5	|equipo SeniorHub	|In Process|
| |	|	T4	|Mensaje de confirmación visual|	Mostrar mensaje “mensaje enviado con éxito” tras enviar el formulario.|	2|	equipo SeniorHub|	Done|
| |	|	T5|	Pruebas funcionales del formulario	|Verificar el correcto envío, validaciones y visualización.|	3	|equipo SeniorHub	|To Review|
    
| User Story |	Work Item / Task |	Id	| Title	| Description |	Estimation (Hours)|	Assigned To |	Status|
|-|-|-|-|-|-|-|-|
| US-32| Call to Action (CTA)	|	T1	|Definición de mensajes CTA	|Crear textos estratégicos para los botones principales (“Contáctanos”, “Conoce más”).|	3	|equipo SeniorHub|	Done|
| | |	T2	|Diseño y ubicación de botones CTA	|Implementar los botones y su posición dentro del landing page.|	3|	equipo SeniorHub |	In Process|
| |	|	T3	|Implementación de anclajes y redirecciones	Configurar redirecciones internas a secciones específicas.|	3|	equipo SeniorHub |	To Review|
|	| |	T4|	Estilos visuales interactivos	| Añadir efectos hover y colores llamativos.|	2	|equipo SeniorHub|	Done |
| |	|	T5|	Prueba de consistencia general	|Verificar que los CTA sean funcionales y coherentes con el diseño.|	2|	equipo SeniorHub |	To Review|

| User Story |	Work Item / Task |	Id	| Title	| Description |	Estimation (Hours)|	Assigned To |	Status|
|-|-|-|-|-|-|-|-|
| US-A01| Implementación de autenticación y roles (Auth Service)	|	T1	|Configurar proyecto base Auth-Service|	Crear proyecto Spring Boot con estructura base y dependencias.|	5|	equipo SeniorHub|	Done|
| |	|	T2|	Implementar autenticación con JWT|	Configurar seguridad y generación de tokens JWT.|	6	|equipo SeniorHub|	In Process|
| |	|	T3|	Crear entidades User, Role y Permission|	Diseñar modelos y relaciones JPA.|	5|	equipo SeniorHub|	Done|
| |	|	T4|	Definir endpoints principales	|Implementar /login, /register y /validate-token.|	6|	equipo SeniorHub| In Process|
| |	|	T5|	Probar autenticación y protección de endpoints|	Validar correcto flujo de autenticación.|	4	|equipo SeniorHub|	To Review|
| |	|	T6	|Documentar configuración de seguridad|	Redactar documentación técnica y README.	|3	|equipo SeniorHub|	Done|

| User Story |	Work Item / Task |	Id	| Title	| Description |	Estimation (Hours)|	Assigned To |	Status|
|-|-|-|-|-|-|-|-|
|US-A02| CRUD de usuarios (User Service)|		T1	|Crear proyecto User-Service|	Generar proyecto Spring Boot para el servicio de usuarios.|	4	|equipo SeniorHub|	Done|
| |	|	T2|	Implementar entidad User y repositorio	|Crear modelo y repositorio JPA.|	3	|equipo SeniorHub|	Done|
|	| |	T3 |	Desarrollar endpoints CRUD|	Implementar GET, POST, PUT, DELETE con validaciones.|	6|	equipo SeniorHub|	In Process|
| |	|	T4|	Conectar con Auth-Service	|Integrar validación JWT con el microservicio de autenticación.|	5|	equipo SeniorHub|	To Review|
| |		|T5|	Documentar endpoints en Swagger|	Añadir especificaciones de API.	|3|equipo SeniorHub|	To Review|

#### 5.2.1.2     Development Evidence for Sprint Review
#### 5.2.1.3     Testing Suite Evidence for Sprint Review
#### 5.2.1.4     Execution Evidence for Sprint Review
#### 5.2.1.5     Microservices Documentation Evidence for Sprint Review

En esta sección de presentan los endpoints desarrollados en el presente sprint y se adjuntan capturas:

<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/52aa1139-2a12-4358-bf9f-d3c288c702f7" />

<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/566f8dfc-36b9-4e1d-b9be-76f9d632abdc" />

#### 5.2.1.6     Software Deployment Evidence for Sprint Review

Aqui se evidencia que el landing page esta desplegado de manera correcta. Link de deployment:[https://seniorhub.vercel.app/](https://seniorhub.vercel.app/)

<div align="center">
<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/34932c24-880b-4102-b7cd-371806f7a36f" />
</div>

#### 5.2.1.7     Team Collaboration Insights during Sprint

A continuación se presentan los insights de colaboración en los repositorios de Github:
Link de organización Github: [https://github.com/1ASI0657-6339-Fund-Arq-Soft](https://github.com/1ASI0657-6339-Fund-Arq-Soft)

Documentation. [https://github.com/1ASI0657-6339-Fund-Arq-Soft/Documentation](https://github.com/1ASI0657-6339-Fund-Arq-Soft/Documentation)
<div align="center">
<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/d2bd97cf-08a4-47dc-8542-8a90e43fec07" />
</div>

<div align="center">
<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/86834b72-b690-4633-8bfc-a2125ab61557" />
</div>

<div align="center">
<img width="1000" height="900" alt="image" src="https://github.com/user-attachments/assets/cccb9000-4793-410e-b5b7-10914895ab29" />
</div>

<div align="center">
<img width="1000" height="600" alt="image" src="https://github.com/user-attachments/assets/e3dc53dd-b8f6-456c-867d-e0260cc2cafe" />
</div>

<div align="center">
<img width="1000" height="800" alt="image" src="https://github.com/user-attachments/assets/fd18650a-2644-464c-ba33-6c8a4efdd583" />
</div>

Landing Page: [https://github.com/1ASI0657-6339-Fund-Arq-Soft/landing-page](https://github.com/1ASI0657-6339-Fund-Arq-Soft/landing-page)

<div align="center">
<img width="1025" height="569" alt="image" src="https://github.com/user-attachments/assets/bb1507cb-2276-469d-8e7b-2ccd5c03bca0" />
</div>

#### 5.2.1.8     Kanban Board --> TP1

El tablero Kanban es una herramienta visual que permite gestionar y monitorear el flujo de trabajo del equipo durante el desarrollo del Sprint 1 del proyecto SeniorHub. Su propósito es asegurar que las tareas se encuentren organizadas y priorizadas, facilitando el seguimiento del progreso de cada historia de usuario desde su planificación hasta su implementación final.

El tablero se estructuró en cuatro columnas principales:

- To Do (Por hacer): Tareas planificadas pendientes de iniciar.
- In Progress (En progreso): Tareas que se encuentran actualmente en desarrollo.
- Review (En revisión): Tareas terminadas que están siendo verificadas y probadas.
- Done (Hecho): Tareas completadas y validadas por el equipo.

**Evidencia del Tablero Kanban**

Herramienta utilizada: Trello.
Sprint: 1
Objetivo del Sprint: Desarrollar el landing page y los microservicios Auth y User para el backend de SeniorHub.
Duración: 28/09/2025 – 9/10/2025

<div align="center">
<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/65488336-1092-402f-8568-f868a151a66a" />
</div>

### 5.2.2	Sprint 2

A continuación, se presentará el sprint planning 2 donde se mostrarán las evidencias de planificación para la implementación de SeniorHub.

| Sprint # |	Sprint 2|
|----------|----------|
||Sprint Planning Background|
| Date |	20/10/2025 |
| Time |	15:00 horas (GMT -5) |
| Location |	Modalidad remota por Discord |
| Prepared By |	Fatima Asmad |
| Attendees (to planning meeting) |	Todos los miembros del equipo SeniorHub |
| Sprint n – 0 Review Summary |	El proyecto ya tenia avanzado en el anterior sprint 2 microservicios , en esta entrega se espera concluir el backend de los microservicios. |
| Sprint n – 1 Retrospective Summary	 | En este presente sprint se tiene como objetivo desarrollar seis microservicos. Asimismo, vamos a conectarlos a la API inicial a través de un API Gateway facilitado por Netflix Eureka y Spring Cloud.|
||Sprint Goal & User Stories|
|Sprint 1 Velocity	|19 |
|Sum of Story Points|	41 |

#### 5.2.2.1	Sprint Backlog 2
#### 5.2.2.2	Development Evidence for Sprint Review
#### 5.2.2.3	Testing Suite Evidence for Sprint Review
#### 5.2.2.4	Execution Evidence for Sprint Review
#### 5.2.2.5	Microservices Documentation Evidence for Sprint Review
#### 5.2.2.6	Software Deployment Evidence for Sprint Review
#### 5.2.2.7	Team Collaboration Insights during Sprint
#### 5.2.2.8	Kanban Board --> (Avance 3)
### 5.2.3	Sprint 3

A continuación, se presentará el sprint planning 3 donde se mostrarán las evidencias de planificación para la implementación de SeniorHub.

| Sprint # |	Sprint 3|
|----------|----------|
||Sprint Planning Background|
| Date |	1/11/2025 |
| Time |	15:00 horas (GMT -5) |
| Location |	Modalidad remota por Discord |
| Prepared By |	Fatima Asmad |
| Attendees (to planning meeting) |	Todos los miembros del equipo SeniorHub |
| Sprint n – 0 Review Summary | En este sprint se espera desarrollar el 40% del frontend del proyecto .|
| Sprint n – 1 Retrospective Summary	 | En este presente sprint se tiene como objetivo desarrollar el  40% del frontend del proyecto.|
||Sprint Goal & User Stories|
|Sprint 1 Velocity	|19 |
|Sum of Story Points|	14|

#### 5.2.3.1	Sprint Backlog 3
#### 5.2.3.2	Development Evidence for Sprint Review
#### 5.2.3.3	Testing Suite Evidence for Sprint Review
#### 5.2.3.4	Execution Evidence for Sprint Review
#### 5.2.3.5	Microservices Documentation Evidence for Sprint Review
#### 5.2.3.6	Software Deployment Evidence for Sprint Review
#### 5.2.3.7	Team Collaboration Insights during Sprint
####  5.2.3.8	Kanban Board --> (Avance 4)












