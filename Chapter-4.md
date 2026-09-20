## **Capítulo IV: Strategic-Level Software Design**

- 4.1. Strategic-Level Attribute-Driven Design
    - 4.1.1. Design Purpose
    El propósito del diseño arquitectónico es definir una solución tecnológica que permita implementar una plataforma digital multicanal orientada al seguimiento clínico-nutricional de mascotas geriátricas y con enfermedades crónicas, garantizando la integración entre los usuarios propietarios, profesionales veterinarios y los servicios tecnológicos asociados.

    La arquitectura propuesta busca establecer una estructura flexible y mantenible mediante el uso de una arquitectura hexagonal, permitiendo separar la lógica de negocio del dominio clínico de los componentes externos de infraestructura, interfaces de usuario y servicios de terceros.

    Asimismo, el diseño considera la necesidad de gestionar información clínica longitudinal, facilitar la comunicación entre veterinarios y propietarios de mascotas, y asegurar la entrega oportuna de recordatorios y actualizaciones mediante mecanismos de autenticación segura, comunicación en tiempo real y servicios de notificación móvil.

    - 4.1.2. Attribute-Driven Design Inputs

        El diseño arquitectónico toma como entradas principales las funcionalidades críticas del sistema, los atributos de calidad requeridos y las restricciones tecnológicas definidas para la solución.
        - 4.1.2.1. Primary Functionality (Primary User Stories)

        Las funcionalidades principales seleccionadas como impulsores arquitectónicos corresponden a aquellas User Stories que tienen mayor impacto en la definición de la estructura del sistema.

        | User Story | Funcionalidad principal | Impacto arquitectónico |
        |---|---|---|
        | US01 | Registrar mascota | Requiere un módulo de gestión de pacientes que permita almacenar y consultar información básica de las mascotas. |
        | US02 | Consultar historial clínico | Requiere una estructura de persistencia capaz de gestionar información clínica histórica y trazabilidad de registros. |
        | US03 | Registrar atención clínica | Requiere un dominio clínico independiente para administrar consultas, tratamientos y evolución del paciente. |
        | US04 | Agendar cita veterinaria | Requiere servicios para gestionar disponibilidad, programación y actualización de citas. |
        | US07 | Configurar recordatorios de medicación | Requiere integración con servicios de notificación para automatizar avisos relacionados con tratamientos. |
        | US08 | Prescribir plan de dieta | Requiere un módulo especializado para gestionar información nutricional asociada a cada mascota. |
        | US10 | Visualizar listado de pacientes | Requiere una interfaz orientada al veterinario para consultar pacientes y realizar seguimiento clínico. |
        | US11 | Consultar evolución de un paciente | Requiere mecanismos para representar indicadores clínicos y analizar cambios durante el tratamiento. |
        | US21 | Iniciar sesión mediante autenticación segura | Requiere un mecanismo centralizado de identidad y control de acceso para proteger la información del sistema. |
        | US22 | Gestionar acceso según rol de usuario | Requiere autorización basada en roles para diferenciar permisos entre propietarios, veterinarios y administradores. |

        Estas funcionalidades representan los principales flujos del negocio y determinan la necesidad de componentes independientes para gestión clínica, identidad, notificaciones y comunicación entre usuarios.

        - 4.1.2.2. Quality Attribute Scenarios}
        - Los atributos de calidad representan las características no funcionales que guían las decisiones arquitectónicas de VetPax. Debido a que la plataforma gestiona información clínica de mascotas, comunicación entre usuarios y servicios externos, se consideran como principales atributos de calidad la seguridad, disponibilidad, escalabilidad, mantenibilidad e interoperabilidad.
        
        ### Seguridad
        
        | Elemento | Descripción |
        |---|---|
        | **Fuente** | Usuario no autorizado |
        | **Estímulo** | Intenta acceder al historial clínico de una mascota sin contar con los permisos correspondientes |
        | **Entorno** | Usuario autenticado dentro de la plataforma móvil o panel web |
        | **Artefacto** | Servicio de autenticación, autorización y módulo de gestión clínica |
        | **Respuesta** | El sistema valida la identidad y permisos del usuario mediante el proveedor de identidad Keycloak, bloqueando accesos que no correspondan al rol asignado |
        | **Medida de respuesta** | Las solicitudes no autorizadas deben ser rechazadas mediante mecanismos de control de acceso, retornando una respuesta de autorización denegada |
        
        ### Disponibilidad
        
        | Elemento | Descripción |
        |---|---|
        | **Fuente** | Dueño de mascota o veterinario |
        | **Estímulo** | Solicita consultar información del historial clínico de una mascota |
        | **Entorno** | Usuarios utilizando la aplicación móvil o panel web |
        | **Artefacto** | Servicios backend y almacenamiento de información clínica |
        | **Respuesta** | El sistema procesa la solicitud y devuelve los registros clínicos disponibles manteniendo la continuidad del seguimiento |
        | **Medida de respuesta** | El servicio debe mantenerse operativo durante la interacción de los usuarios, permitiendo consultas de información clínica sin pérdida de datos |
        
        ### Escalabilidad
        
        | Elemento | Descripción |
        |---|---|
        | **Fuente** | Nuevos usuarios y veterinarias incorporadas a la plataforma |
        | **Estímulo** | Incremento en la cantidad de usuarios registrados y solicitudes simultáneas |
        | **Entorno** | Etapa de crecimiento de VetPax |
        | **Artefacto** | Servicios backend, APIs y base de datos |
        | **Respuesta** | La arquitectura permite ampliar la capacidad del sistema mediante la incorporación de nuevos recursos sin modificar la lógica principal del dominio |
        | **Medida de respuesta** | El sistema debe soportar el crecimiento progresivo de usuarios manteniendo tiempos de respuesta adecuados |
        
        ### Mantenibilidad
        
        | Elemento | Descripción |
        |---|---|
        | **Fuente** | Equipo de desarrollo |
        | **Estímulo** | Requiere modificar una funcionalidad existente o agregar nuevas capacidades |
        | **Entorno** | Durante actividades de mantenimiento y evolución del sistema |
        | **Artefacto** | Arquitectura interna del backend |
        | **Respuesta** | La arquitectura hexagonal permite separar la lógica de negocio de componentes externos, facilitando modificaciones independientes |
        | **Medida de respuesta** | Los cambios realizados deben afectar únicamente al componente correspondiente, reduciendo impactos sobre otros módulos del sistema |
        
        ### Interoperabilidad
        
        | Elemento | Descripción |
        |---|---|
        | **Fuente** | Servicios externos integrados |
        | **Estímulo** | Comunicación con proveedores externos como Keycloak, Firebase Cloud Messaging o servicios de comunicación en tiempo real |
        | **Entorno** | Operación normal de la plataforma |
        | **Artefacto** | Capa de infraestructura y adaptadores externos |
        | **Respuesta** | El sistema utiliza interfaces desacopladas para comunicarse con servicios externos, permitiendo reemplazar proveedores sin afectar el dominio principal |
        | **Medida de respuesta** | Las integraciones externas deben funcionar mediante componentes independientes, manteniendo estable la lógica del negocio |   
        - 4.1.2.3. Constraints
        Las restricciones consideradas para el diseño arquitectónico son las siguientes:

        | Restricción | Descripción |
        |---|---|
        | Arquitectura del sistema | La solución debe implementarse bajo una arquitectura hexagonal para desacoplar la lógica de negocio de frameworks, bases de datos y servicios externos. |
        | Plataforma multicanal | El sistema debe permitir interacción mediante una aplicación móvil orientada a propietarios y una aplicación web orientada a veterinarios. |
        | Seguridad de acceso | La autenticación y autorización deben gestionarse mediante un proveedor externo de identidad basado en Keycloak, permitiendo administrar usuarios y roles. |
        | Comunicación en tiempo real | La plataforma debe permitir actualizaciones bidireccionales entre clientes mediante WebSockets para reflejar cambios clínicos y eventos relevantes. |
        | Notificaciones móviles | El sistema debe integrar Firebase Cloud Messaging para enviar recordatorios relacionados con medicación, alimentación y citas. |
        | Gestión de información clínica | La solución debe conservar la trazabilidad de historiales, tratamientos y planes nutricionales asociados a cada mascota. |
        | Separación de responsabilidades | Los componentes del sistema deben mantener independencia entre dominio, aplicación e infraestructura para facilitar mantenimiento y evolución futura. |
    - 4.1.3. Architectural Drivers Backlog
            - El Architectural Drivers Backlog identifica y prioriza los principales factores que influyen en las decisiones arquitectónicas de VetPax. Estos drivers incluyen requerimientos funcionales críticos, atributos de calidad y restricciones técnicas que determinan la estructura del sistema.
        
        La priorización considera el impacto arquitectónico de cada elemento, donde los drivers con mayor prioridad representan aquellos que condicionan directamente la selección de estilos arquitectónicos, componentes y tecnologías utilizadas.
        
        | Prioridad | Architectural Driver | Tipo | Descripción | Impacto arquitectónico |
        |---|---|---|---|---|
        | AD01 | Separación de responsabilidades mediante arquitectura hexagonal | Restricción / Mantenibilidad | El sistema debe separar la lógica del dominio clínico de componentes externos como bases de datos, interfaces y servicios de terceros. | Define la estructura principal del backend mediante capas de dominio, aplicación e infraestructura. |
        | AD02 | Seguridad y control de acceso basado en roles | Calidad / Seguridad | La plataforma debe proteger la información clínica permitiendo diferentes permisos para dueños, veterinarios y administradores. | Requiere integración con un proveedor de identidad como Keycloak y mecanismos de autorización por roles. |
        | AD03 | Gestión del historial clínico de mascotas | Funcionalidad crítica | El sistema debe permitir registrar, consultar y mantener la trazabilidad de información clínica de mascotas geriátricas o con enfermedades crónicas. | Requiere un dominio clínico independiente con modelos de persistencia adecuados. |
        | AD04 | Comunicación entre veterinarios y propietarios | Funcionalidad / Interoperabilidad | La plataforma debe permitir sincronizar información entre la aplicación móvil y el panel web veterinario. | Requiere APIs y mecanismos de comunicación en tiempo real mediante WebSockets. |
        | AD05 | Sistema de notificaciones automáticas | Funcionalidad / Disponibilidad | Los usuarios deben recibir recordatorios relacionados con medicación, alimentación y citas. | Requiere integración con servicios externos como Firebase Cloud Messaging. |
        | AD06 | Escalabilidad del sistema | Calidad / Escalabilidad | La solución debe soportar el crecimiento progresivo de usuarios, mascotas registradas y veterinarias afiliadas. | Influye en la modularidad de servicios y diseño desacoplado de componentes. |
        | AD07 | Gestión de planes nutricionales personalizados | Funcionalidad crítica | Los veterinarios deben registrar planes alimenticios asociados a la condición de cada mascota. | Requiere un módulo especializado para administrar información nutricional y evolución del tratamiento. |
        | AD08 | Evolución independiente de componentes | Calidad / Mantenibilidad | La plataforma debe permitir modificar funcionalidades e integrar nuevos servicios sin afectar el núcleo del negocio. | Justifica el uso de interfaces, adaptadores y bajo acoplamiento entre módulos. |
        | AD09 | Disponibilidad del sistema | Calidad / Disponibilidad | Los usuarios deben acceder continuamente a información clínica y recordatorios necesarios para el seguimiento. | Requiere mecanismos para evitar pérdida de información y garantizar continuidad operativa. |
        | AD10 | Integración con servicios externos | Restricción / Interoperabilidad | La plataforma debe comunicarse con servicios externos para autenticación, notificaciones y comunicación. | Requiere una capa de infraestructura desacoplada mediante adaptadores externos. |
        
        Los drivers arquitectónicos identificados orientan las siguientes decisiones de diseño, definiendo la arquitectura hexagonal, la separación por dominios funcionales, la integración con servicios externos y los mecanismos necesarios para garantizar seguridad, mantenibilidad y escalabilidad.
    - 4.1.4. Architectural Design Decisions
    - 4.1.5. Quality Attribute Scenario Refinements

- 4.2. Strategic-Level Domain-Driven Design
    - 4.2.1. EventStorming
    - 4.2.2. Candidate Context Discovery
    - 4.2.3. Domain Message Flows Modeling
    - 4.2.4. Bounded Context Canvases
    - 4.2.5. Context Mapping

- 4.3. Software Architecture
    - 4.3.1. Software Architecture System Landscape Diagram
    - 4.3.2. Software Architecture Context Level Diagrams
    - 4.3.3. Software Architecture Container Level Diagrams
    - 4.3.4. Software Architecture Deployment Diagrams
