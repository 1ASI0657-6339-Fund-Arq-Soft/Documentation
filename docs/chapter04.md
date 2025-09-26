## Capítulo IV: Product Architecture Design

### 4.1	Desing Concepts, ViewPoints & ER Diagrams

#### 4.1.1	Principles Statements

Para el desarrollo del proyecto SeniorHub, aplicaremos los principios SOLID, fundamentales en la programación orientada a objetos y en el diseño de software modular. Esto garantizará que nuestro sistema sea escalable, mantenible y fácil de extender, asegurando una correcta gestión de los residentes, el personal médico y los familiares.

Los principios que guiarán nuestro diseño son:

**S - Single Responsibility Principle (SRP):**

Cada clase y módulo del sistema debe cumplir con una única responsabilidad. Por ejemplo, la clase encargada de gestionar notificaciones solo debe ocuparse de crear, enviar y almacenar notificaciones, sin involucrarse en la lógica de usuarios o reportes.

**O - Open/Closed Principle (OCP):**

El sistema debe estar abierto a la extensión de nuevas funcionalidades (por ejemplo, la incorporación de un nuevo tipo de reporte o la integración con un servicio externo de mensajería), pero cerrado a modificaciones que afecten la estabilidad del código existente.

**L - Liskov Substitution Principle (LSP):**

Las entidades hijas deben poder sustituir a sus entidades padre sin alterar el comportamiento esperado. En SeniorHub, por ejemplo, un “Usuario Familiar” debería comportarse correctamente en cualquier lugar donde se use un “Usuario”, sin romper la lógica del sistema.

**I - Interface Segregation Principle (ISP):**

Las interfaces deben ser específicas y no forzar a las clases a implementar métodos que no necesitan. Por ejemplo, una interfaz INotificationService puede dividirse en subinterfaces como ISendNotification y IArchiveNotification, evitando que un módulo que solo envía notificaciones deba implementar funciones de archivado.

**D - Dependency Inversion Principle (DIP):**

Los módulos de alto nivel (como el gestor de reportes médicos) no deben depender directamente de los módulos de bajo nivel (como la base de datos). Ambos deben depender de abstracciones (interfaces o servicios). Esto permitirá cambiar la tecnología de persistencia (por ejemplo, de SQL a NoSQL) sin alterar la lógica de negocio.

#### 4.1.2	Approaches Statements Architectural Styles & Patterns

#### 4.1.3	 Context Diagram

#### 4.1.4	Approach driven ViewPoints Diagrams

#### 4.1.5	Relational/Non Relational Database Diagram 

#### 4.1.6	Design Patterns

#### 4.1.7	Tactics

### 4.2	Architectural Drivers

#### 4.2.1	Design Purpose

#### 4.2.2	Primary Functionality (Primary User Stories)

#### 4.2.3	Quality Attribute Scenarios

#### 4.2.4	Constraints

#### 4.2.5	Architectural Concerns

### 4.3	ADD Iterations

#### 4.3.X	Iteration N: <Iteration Name>

#### 4.3.X.1	Architectural Design Backlog N

#### 4.3.X.2	Establish Iteration Goal by Selecting Drivers

#### 4.3.X.3	Choose One or More Elements of the System to Refine

#### 4.3.X.4	Choose One or More Design Concepts That Satisfy the Selected Drivers

#### 4.3.X.5	Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces

#### 4.3.X.6	Sketch Views (C4 & UML) and Record Design Decisions

#### 4.3.X.7	Analysis of Current Design and Review Iteration Goal (Kanban Board)  (Avance 2)

