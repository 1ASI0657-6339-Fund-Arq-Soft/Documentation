# Final-Report
![Logo de UPC](https://i.ibb.co/4ZtdQrX4/logoUPC.png)

# Universidad Peruana de Ciencias Aplicadas

## Carrera de Ingeniería de Software

Ciclo: 2025 - 20

Curso: Fundamentos de la Arquitectura de Software  

Sección: 6339

Profesor: Ernesto Ocampo Tello

"Informe de Avance 1"

Startup: DevElevate

Producto: SeniorHub

Grupo: 02

|           Integrantes            |   Código   |
| :------------------------------: | :--------: |
|   Fatima Andrea Asmad Padilla  | U20221b490 |
|  Andrés Fernado Rodriguez Zuluoeta  |u202124213 |
| Fabian Alonso Reyes Trujillano | U202218233|


Agosto 2025

# Registro de Versiones del Informe

| Versión | Fecha | Autor | Descripción de modificación |
| ------- | ----- | ----- | --------------------------- |
| v 1.0 | 04/09/2025 | Fabian Alonso Reyes Trujillano | Creacion del proyecto |
| v 1.1 | 08/09/2025 | Fatima Andrea Asmad Padilla | Dearrollo capitulo 1 y 2 |
| v 1.2 | 09/09/2025 | Andrés Fernado Rodriguez Zuluoeta | Se agrego entrevistas y analisis de estas|
| v 1.3 | 10/09/2025 | Fatima Andrea Asmad Padilla | Se agrego el punto 2.3 Needfinding |
| v 1.4 | 10/09/2025 | Fabian Alonso Reyes Trujillano y Andrés Fernado Rodriguez Zuluoeta | Se agrego el capitulo 3 |
| v 1.5 | 11/09/2025 | Fatima Andrea Asmad Padilla | Se agregaron los requisitos funcionales y se hicieron ultimas correcciones |

# Project Report Collaboration Insights

URL Project Report (Github): [https://github.com/1ASI0657-6339-Fund-Arq-Soft/Documentation](https://github.com/1ASI0657-6339-Fund-Arq-Soft/Documentation)

# Contenido
## Tabla de Contenido

### Capítulo I: Introducción
- [1.1. Startup Profile](#11-startup-profile)
  - [1.1.1. Descripción de la Startup](#111-descripción-de-la-startup)
  - [1.1.2. Perfiles de integrantes del equipo](#112-perfiles-de-integrantes-del-equipo)
- [1.2. Solution Profile](#12-solution-profile)
  - [1.2.1. Nombre del producto](#121-nombre-del-producto)
  - [1.2.2. Antecedentes y problemática](#122-antecedentes-y-problemática)
  - [1.2.3. Lean UX Process](#123-lean-ux-process)
    - [1.2.3.1. Lean UX Problem Statement](#1231-lean-ux-problem-statement)
    - [1.2.3.2. Lean UX Assumptions](#1232-lean-ux-assumptions)
    - [1.2.3.3. Lean UX Hypothesis](#1233-lean-ux-hypothesis)
    - [1.2.3.4. Lean UX Canvas](#1234-lean-ux-canvas)
- [1.3. Segmentos objetivo](#13-segmentos-objetivo)

### Capítulo II: Requirements & Analysis
- [2.1. Competidores](#21-competidores)
- [2.2. Entrevistas](#22-entrevistas)
- [2.3. Needfinding](#23-needfinding)
  - [2.3.1. User Personas](#231-user-personas)
  - [2.3.2. User Task Matrix](#232-user-task-matrix)
  - [2.3.3. Empathy Maps](#233-empathy-maps)
  - [2.3.4. As-is Scenario Mapping](#234-as-is-scenario-mapping)

### Capítulo III: Requirements Specification
- [3.1. To-Be Scenario Mapping](#31-to-be-scenario-mapping)
- [3.2. User Stories](#32-user-stories)
- [3.3. Impact Map](#33-impact-map)
- [3.4. Product Backlog (Avance1)](#34-product-backlog-avance1)

### Capítulo IV: Product Architecture Design
- [4.1. Desing Concepts, ViewPoints & ER Diagrams](#41-desing-concepts-viewpoints--er-diagrams)
  - [4.1.1. Principles Statements](#411-principles-statements)
  - [4.1.2. Approaches Statements Architectural Styles & Patterns](#412-approaches-statements-architectural-styles--patterns)
  - [4.1.3. Context Diagram](#413-context-diagram)
  - [4.1.4. Approach driven ViewPoints Diagrams](#414-approach-driven-viewpoints-diagrams)
  - [4.1.5. Relational/Non Relational Database Diagram](#415-relationalnon-relational-database-diagram)
  - [4.1.6. Design Patterns](#416-design-patterns)
  - [4.1.7. Tactics](#417-tactics)
- [4.2. Architectural Drivers](#42-architectural-drivers)
  - [4.2.1. Design Purpose](#421-design-purpose)
  - [4.2.2. Primary Functionality (Primary User Stories)](#422-primary-functionality-primary-user-stories)
  - [4.2.3. Quality Attribute Scenarios](#423-quality-attribute-scenarios)
  - [4.2.4. Constraints](#424-constraints)
  - [4.2.5. Architectural Concerns](#425-architectural-concerns)
- [4.3. ADD Iterations](#43-add-iterations)
  - [4.3.X. Iteration N: <Iteration Name>](#43x-iteration-n-iteration-name)
    - [4.3.X.1. Architectural Design Backlog N](#43x1-architectural-design-backlog-n)
    - [4.3.X.2. Establish Iteration Goal by Selecting Drivers](#43x2-establish-iteration-goal-by-selecting-drivers)
    - [4.3.X.3. Choose One or More Elements of the System to Refine](#43x3-choose-one-or-more-elements-of-the-system-to-refine)
    - [4.3.X.4. Choose One or More Design Concepts That Satisfy the Selected Drivers](#43x4-choose-one-or-more-design-concepts-that-satisfy-the-selected-drivers)
    - [4.3.X.5. Instantiate Architectural Elements, Allocate Responsibilities, and Define Interfaces](#43x5-instantiate-architectural-elements-allocate-responsibilities-and-define-interfaces)
    - [4.3.X.6. Sketch Views (C4 & UML) and Record Design Decisions](#43x6-sketch-views-c4--uml-and-record-design-decisions)
    - [4.3.X.7. Analysis of Current Design and Review Iteration Goal (Kanban Board) (Avance 2)](#43x7-analysis-of-current-design-and-review-iteration-goal-kanban-board-avance-2)

### Capítulo V: Product Implementation, Validation & Deployment
- [5.1. Testing Suites & General Patterns](#51-testing-suites--general-patterns)
  - [5.1.1. Backend Application Core Testing Suite](#511-backend-application-core-testing-suite)
  - [5.1.2. Pattern Based Backend Application(s)](#512-pattern-based-backend-applications)
  - [5.1.3. Pattern Based Custom Software Library](#513-pattern-based-custom-software-library)
  - [5.1.4. Framework Pattern Driven Refactoring Report](#514-framework-pattern-driven-refactoring-report)
- [5.2. Software Configuration Management](#52-software-configuration-management)
  - [5.2.1. Software Development Environment Configuration](#521-software-development-environment-configuration)
  - [5.2.2. Source Code Management](#522-source-code-management)
  - [5.2.3. Source Code Style Guide & Conventions](#523-source-code-style-guide--conventions)
  - [5.2.4. Software Deployment Configuration](#524-software-deployment-configuration)
- [5.3. Microservices Implementation](#53-microservices-implementation)
  - [5.3.1. Sprint 1](#531-sprint-1)
    - [5.3.1.1. Sprint Backlog 1](#5311-sprint-backlog-1)
    - [5.3.1.2. Development Evidence for Sprint Review](#5312-development-evidence-for-sprint-review)
    - [5.3.1.3. Testing Suite Evidence for Sprint Review](#5313-testing-suite-evidence-for-sprint-review)
    - [5.3.1.4. Execution Evidence for Sprint Review](#5314-execution-evidence-for-sprint-review)
    - [5.3.1.5. Microservices Documentation Evidence for Sprint Review](#5315-microservices-documentation-evidence-for-sprint-review)
    - [5.3.1.6. Software Deployment Evidence for Sprint Review](#5316-software-deployment-evidence-for-sprint-review)
    - [5.3.1.7. Team Collaboration Insights during Sprint](#5317-team-collaboration-insights-during-sprint)
    - [5.3.1.8. Kanban Board --> TP1](#5318-kanban-board----tp1)
  - [5.3.2. Sprint 2](#532-sprint-2)
    - [5.3.2.1. Sprint Backlog 2](#5321-sprint-backlog-2)
    - [5.3.2.2. Development Evidence for Sprint Review](#5322-development-evidence-for-sprint-review)
    - [5.3.2.3. Testing Suite Evidence for Sprint Review](#5323-testing-suite-evidence-for-sprint-review)
    - [5.3.2.4. Execution Evidence for Sprint Review](#5324-execution-evidence-for-sprint-review)
    - [5.3.2.5. Microservices Documentation Evidence for Sprint Review](#5325-microservices-documentation-evidence-for-sprint-review)
    - [5.3.2.6. Software Deployment Evidence for Sprint Review](#5326-software-deployment-evidence-for-sprint-review)
    - [5.3.2.7. Team Collaboration Insights during Sprint](#5327-team-collaboration-insights-during-sprint)
    - [5.3.2.8. Kanban Board --> (Avance 3)](#5328-kanban-board----avance-3)
  - [5.3.3. Sprint 3](#533-sprint-3)
    - [5.3.3.1. Sprint Backlog 3](#5331-sprint-backlog-3)
    - [5.3.3.2. Development Evidence for Sprint Review](#5332-development-evidence-for-sprint-review)
    - [5.3.3.3. Testing Suite Evidence for Sprint Review](#5333-testing-suite-evidence-for-sprint-review)
    - [5.3.3.4. Execution Evidence for Sprint Review](#5334-execution-evidence-for-sprint-review)
    - [5.3.3.5. Microservices Documentation Evidence for Sprint Review](#5335-microservices-documentation-evidence-for-sprint-review)
    - [5.3.3.6. Software Deployment Evidence for Sprint Review](#5336-software-deployment-evidence-for-sprint-review)
    - [5.3.3.7. Team Collaboration Insights during Sprint](#5337-team-collaboration-insights-during-sprint)
    - [5.3.3.8. Kanban Board --> (Avance 4)](#5338-kanban-board----avance-4)
  - [5.3.4. Sprint 4](#534-sprint-4)
    - [5.3.4.1. Sprint Backlog 4](#5341-sprint-backlog-4)
    - [5.3.4.2. Development Evidence for Sprint Review](#5342-development-evidence-for-sprint-review)
    - [5.3.4.3. Testing Suite Evidence for Sprint Review](#5343-testing-suite-evidence-for-sprint-review)
    - [5.3.4.4. Execution Evidence for Sprint Review](#5344-execution-evidence-for-sprint-review)
    - [5.3.4.5. Microservices Documentation Evidence for Sprint Review](#5345-microservices-documentation-evidence-for-sprint-review)
    - [5.3.4.6. Software Deployment Evidence for Sprint Review](#5346-software-deployment-evidence-for-sprint-review)
    - [5.3.4.7. Team Collaboration Insights during Sprint](#5347-team-collaboration-insights-during-sprint)
    - [5.3.4.8. Kanban Board](#5348-kanban-board)
- [5.4. Microservices Deployment](#54-microservices-deployment)
  - [5.4.1. Cloud Architecture Diagram](#541-cloud-architecture-diagram)
  - [5.4.2. Cloud Architecture Deployment (AWS, Microsoft Azure or Google Cloud)](#542-cloud-architecture-deployment-aws-microsoft-azure-or-google-cloud)
# Student Outcome

**ABET – EAC - Student Outcome 7**

Aprendizaje Continuo y Autónomo

*Criterio: La capacidad de adquirir y aplicar nuevos conocimientos según sea necesario, utilizando estrategias de aprendizaje apropiadas*

En el siguiente cuadro se describe las acciones realizadas y enunciados de conclusiones por parte del equipo, que permiten sustentar el haber alcanzado el logro del ABET – EAC - Student Outcome.

| Criterio Específico | Acciones Realizadas | Conclusiones |
|---------------------|---------------------|--------------|
| **Actualiza conceptos y conocimientos necesarios para su desarrollo profesional y en especial para su proyecto en soluciones de software.** | **TB1** <br>-Fabian Reyes Trujillano: Aplicó metodologías ágiles para estructurar el backlog y escenarios futuros, incorporando buenas prácticas de arquitectura de software. <br>-Fatima Asmad Padilla: Investigó y aplicó el proceso Lean UX, desarrolló perfiles de usuario y mapas de empatía, integrando conceptos modernos de diseño centrado en el usuario. <br> -Andrés Rodriguez Zuluoeta: Desarrolló el Impact Map y realizó análisis estratégico de entrevistas, aplicando conceptos de planificación y priorización de funcionalidades. <br>| **TB1** <br>-Fabian Reyes Trujillano: Mostró dominio de herramientas ágiles y técnicas modernas de especificación de requisitos. <br>-Fatima Asmad Padilla: Demostró capacidad para integrar nuevos conceptos de UX y análisis de usuarios en el desarrollo del proyecto. <br> -Andrés Rodriguez Zuluoeta: Aplicó conocimientos estratégicos para definir el impacto del producto y sus funcionalidades clave. |
| **Reconoce la necesidad del aprendizaje permanente para el desempeño profesional y el desarrollo de proyectos en soluciones de software.** |**TB1** <br>-Fabian Reyes Trujillano: Adaptó sus conocimientos técnicos al contexto del proyecto, mostrando apertura a nuevas herramientas y enfoques de desarrollo. <br>-Fatima Asmad Padilla: Participó activamente en entrevistas y análisis de usuarios, demostrando disposición para aprender de la experiencia directa con stakeholders. <br> -Andrés Rodriguez Zuluoeta: Reconoció la importancia de entender al usuario final y de actualizar sus habilidades para contribuir al desarrollo del producto. <br>| **TB1** <br>-Fabian Reyes Trujillano: Reflejó compromiso con el aprendizaje permanente para mejorar su desempeño profesional. <br>-Fatima Asmad Padilla: Evidenció actitud proactiva hacia el aprendizaje continuo y la mejora del diseño del producto. <br> -Andrés Rodriguez Zuluoeta: Mostró conciencia sobre la necesidad de actualizar sus conocimientos para aportar valor al proyecto.|


## [Conclusiones](/report/chapter5/chapter-5.md#conclusiones)

## [Video About-The-Team](/report/chapter5/chapter-5.md#video-about-the-team)

## [Bibliografía](/report/chapter5/chapter-5.md#bibliografía)

## [Anexos](/report/chapter5/chapter-5.md#anexos)
