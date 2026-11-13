<div style="page-break-after: always;"></div>

## Conclusiones

1. El desarrollo de **VetPax** permitió delimitar una propuesta de valor centrada en la continuidad del cuidado de mascotas geriátricas o con enfermedades crónicas. A diferencia de un sistema orientado exclusivamente a la administración interna de una clínica, la solución relaciona las necesidades de propietarios y profesionales veterinarios mediante el historial clínico, las citas, los tratamientos de medicación y los planes de alimentación. El análisis de VetOS, PetSuite, GVET, VetFac y SmartVet360 permitió reconocer capacidades comunes del mercado y precisar el enfoque de seguimiento longitudinal de VetPax.

2. Las actividades de *Requirements Elicitation & Analysis* y las entrevistas exploratorias a los segmentos objetivo permitieron identificar dificultades relacionadas con la disponibilidad de información clínica, la organización de los controles y el cumplimiento de indicaciones entre consultas. Estas necesidades se tradujeron en requisitos funcionales y no funcionales, siete Epic Stories y un Product Backlog compuesto por User Stories y Technical Stories con criterios de aceptación. La especificación diferencia las responsabilidades del propietario, que consulta información y registra actividades de cuidado, de las del profesional veterinario, que registra atenciones y prescribe tratamientos y planes nutricionales.

3. Los antecedentes internacionales respaldan la pertinencia de evaluar herramientas digitales para apoyar el seguimiento veterinario. PetDesk comunicó una reducción de inasistencias del 11 % a menos del 3 % en el caso de una clínica de San Diego; por su parte, Silva (2023) registró 54 asistencias a consultas de revacunación en los grupos que recibieron mensajes digitales, frente a cuatro en el grupo de control. Estos resultados constituyen antecedentes de otras poblaciones y contextos, no indicadores de efectividad ya obtenidos por VetPax.

4. La aplicación de **Domain-Driven Design, EventStorming y Bounded Context Mapping** permitió identificar siete contextos: *Pet & Clinical Care, Appointment Management, Medication Treatment, Nutrition Management, Clinic Management, Adherence & Gamification* e *Identity & Access Management*. Esta división establece responsabilidades sobre entidades, reglas de negocio y datos, y organiza su colaboración mediante identificadores, contratos de aplicación y eventos. Su implementación como **monolito modular** permite mantener límites lógicos de dominio sin asumir el costo operativo de siete microservicios independientes.

5. La adopción de **Hexagonal Architecture** orientó la separación entre Domain, Application, Infrastructure e Interface. El backend se desarrolló con **C# y ASP.NET Core/.NET 10**, exponiendo servicios REST mediante contratos OpenAPI y organizando la persistencia con Entity Framework Core y MySQL. Esta estructura permite mantener las decisiones de negocio en el dominio y encapsular el acceso a datos y a servicios externos mediante puertos y adaptadores, favoreciendo la evolución de los módulos.

6. La seguridad de la solución se fundamenta en la integración con **Keycloak** para autenticación e identidad y en políticas de autorización propias de VetPax para acceder a recursos clínicos. El rol de veterinario no constituye, por sí solo, una autorización para consultar cualquier paciente: la operación depende también de las relaciones entre usuario, clínica y mascota. Se diferencia, asimismo, la vigencia técnica del token de acceso de la vigencia del vínculo o permiso clínico, conservando una separación entre identidad y reglas de acceso del negocio.

7. El diseño del módulo **Medication Treatment** incorporó restricciones para la consistencia de las prescripciones y de su seguimiento: fechas válidas, dosis y horarios de administración definidos, prevención de coincidencias de horarios en los mismos días y control de administraciones repetidas. Para el procesamiento de recordatorios se identificaron mecanismos de control concurrente basados en estados y bloqueos temporales, relevantes cuando distintos procesos intentan atender el mismo evento. Estas medidas responden al requisito de preservar la integridad del registro clínico y reducir el procesamiento duplicado.

8. Las decisiones de disponibilidad y resiliencia consideran las dependencias que introduce el despliegue de un único backend con almacenamiento compartido. La persistencia de negocio en **MySQL** y la persistencia de identidad de **Keycloak en PostgreSQL** requieren estrategias diferenciadas de recuperación. En el diseño se definieron objetivos de recuperación **RTO de 60 minutos y RPO de 15 minutos**, como metas técnicas y no como resultados ya medidos. La separación entre operaciones confirmadas, fallos de servicios externos y reintentos permite describir un comportamiento consistente sin equiparar la existencia de respaldos con alta disponibilidad automática.

9. La implementación de los productos digitales estableció una experiencia diferenciada: **Landing Page** informativa, aplicación web desarrollada con **Angular** para el segmento veterinario y aplicación móvil desarrollada con **Flutter** para los propietarios. Los entregables de *Solution UX Design* —arquitectura de información, wireframes, mock-ups, wireflows, diagramas de flujo de usuario y prototipos— proporcionaron una referencia común para relacionar los recorridos de usuario con la implementación y los contratos del backend.

10. Durante el **Sprint 1, del 27 de octubre al 13 de noviembre de 2026**, el equipo organizó en Jira un compromiso de **10 Story Points**, correspondiente a **US15, US16, US19 y TS11**, asociados con la presencia digital y la captación de usuarios. La Landing Page se publicó en **Netlify** y se documentó mediante **24 capturas de ejecución**, distribuidas en 13 vistas de escritorio y 11 vistas móviles. Estas evidencias respaldan la presentación del producto y su adaptación responsive; la visibilidad de los botones de acceso se distingue de la comprobación de sus destinos y del funcionamiento integral del registro de interesados.

11. El control de versiones y la colaboración se desarrollaron mediante cinco repositorios de GitHub para el informe, el backend, la aplicación web, la aplicación móvil y la Landing Page. La revisión de **40 ramas** entre `main`, `develop` y `feature/*` permitió reconocer el trabajo por capacidad y su integración mediante *pull requests*, sin limitar el análisis a la rama principal. Esta trazabilidad vincula los cambios de código con la evolución de los productos digitales y complementa el seguimiento de las historias de Jira.

12. La validación técnica del backend cuenta con una suite automatizada documentada mediante capturas del explorador de pruebas de JetBrains Rider: **274 elementos contabilizados, de los cuales 263 resultaron exitosos y 11 fueron omitidos o ignorados**, sin fallos visibles en dicha ejecución. Los casos abarcan pruebas de API, aplicación, dominio, infraestructura, integración y aceptación. En conjunto, los requisitos, las decisiones arquitectónicas, los modelos tácticos, los repositorios, las pruebas y las evidencias de despliegue conforman una base verificable para la evolución gradual de VetPax, distinguiendo los resultados observados de los atributos de calidad definidos como objetivos de diseño.

---

## Bibliografía

### Documentos del curso

- Universidad Peruana de Ciencias Aplicadas. (2024). *SI728 Arquitecturas de Software Emergentes: Enunciado del Trabajo Final*. Facultad de Ingeniería, Universidad Peruana de Ciencias Aplicadas.
- Universidad Peruana de Ciencias Aplicadas. (2026). *Rúbrica ABET – 1ASI0728 Arquitecturas de Software Emergentes*. Facultad de Ingeniería, Universidad Peruana de Ciencias Aplicadas.
- Universidad Peruana de Ciencias Aplicadas. (2026). *Rúbrica de Logro – 1ASI0728 Arquitecturas de Software Emergentes*. Facultad de Ingeniería, Universidad Peruana de Ciencias Aplicadas.

### Competidores y soluciones veterinarias

- VetOS. (s. f.). *VetOS: Software veterinario en la nube*. https://www.sistemavetos.com/
- PetSuite. (s. f.). *PetSuite: Software de gestión para veterinarias*. https://petsuite.pe/
- GVET. (s. f.). *Software veterinario para gestionar tu clínica*. https://g.vet/es/
- VetFac. (s. f.). *Software veterinario con facturación electrónica*. https://vetfac.pe/
- SmartVet360. (s. f.). *Software veterinario en la nube*. https://smartvet360.com/

### Antecedentes internacionales y evidencia de soluciones veterinarias digitales

- PetDesk. (s. f.). *Increased revenue by over $225K with PetDesk*. https://petdesk.com/resources/increased-revenue-with-petdesk
- Silva, B. I. S. (2023). *O potencial das ferramentas digitais no incentivo ao cumprimento de programas vacinais por detentores de cães* [Disertación de maestría, Universidade de Lisboa, Faculdade de Medicina Veterinária]. Repositório da Universidade de Lisboa. https://hdl.handle.net/10400.5/28425

### Arquitectura de software y diseño del dominio

- Evans, E. (2003). *Domain-driven design: Tackling complexity in the heart of software*. Addison-Wesley.
- Vernon, V. (2013). *Implementing domain-driven design*. Addison-Wesley.
- Richardson, C. (2018). *Microservices patterns: With examples in Java*. Manning Publications.
- Brandolini, A. (s. f.). *EventStorming*. https://www.eventstorming.com/
- Microsoft. (s. f.). *Handling concurrency conflicts: Entity Framework Core*. Microsoft Learn. https://learn.microsoft.com/en-us/ef/core/saving/concurrency

### Tecnologías, seguridad, documentación de APIs y despliegue

- Microsoft. (s. f.). *ASP.NET Core web API documentation with Swagger / OpenAPI*. Microsoft Learn. https://learn.microsoft.com/en-us/aspnet/core/tutorials/web-api-help-pages-using-swagger/
- Keycloak. (s. f.). *Server Administration Guide*. https://www.keycloak.org/docs/latest/server_admin/
- Google. (s. f.). *Firebase Cloud Messaging*. Firebase Documentation. https://firebase.google.com/docs/cloud-messaging
- Mozilla. (s. f.). *WebSocket API (WebSockets)*. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API
- Railway. (s. f.). *Databases*. Railway Docs. https://docs.railway.com/databases
- Railway. (s. f.). *Backups*. Railway Docs. https://docs.railway.com/volumes/backups
- Angular. (s. f.). *Angular documentation*. https://angular.dev/
- Flutter. (s. f.). *Flutter documentation*. https://docs.flutter.dev/
- Netlify. (s. f.). *Netlify documentation*. https://docs.netlify.com/
- GitHub. (s. f.). *GitHub Docs*. https://docs.github.com/

### Experiencia de usuario y desarrollo de producto

- Gothelf, J., & Seiden, J. (2021). *Lean UX: Designing great products with agile teams*. O'Reilly Media.
- Cohn, M. (2004). *User stories applied: For agile software development*. Addison-Wesley.

### Fuentes primarias del proyecto VetPax

- PawVital Tech. (2026). *VetPax-Report* [Repositorio de documentación]. GitHub. https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Report
- PawVital Tech. (2026). *VetPax-Backend* [Repositorio de código fuente]. GitHub. https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Backend
- PawVital Tech. (2026). *VetPax-Web_Application* [Repositorio de código fuente]. GitHub. https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Web_Application
- PawVital Tech. (2026). *VetPax-Mobile_Application* [Repositorio de código fuente]. GitHub. https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Mobile_Application
- PawVital Tech. (2026). *VetPax-Landing_Page* [Repositorio de código fuente]. GitHub. https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Landing_Page

---

## Anexo

### EventStorming

- **EventStorming de VetPax:** [Consultar tablero en Miro](https://miro.com/app/board/uXjVHk77Zs8=/?share_link_id=766277899100).

### Prototipos de Figma

- **VetPax Mobile Application Prototype:** [Consultar prototipo móvil en Figma](https://www.figma.com/proto/w9edhFA6VCAvT7Rl3wKKe2/Mobil-Application?node-id=22-2411&t=CR6IkEqjYgPmg0Kf-1&scaling=min-zoom&content-scaling=fixed&page-id=20%3A2&starting-point-node-id=22%3A2475).
- **VetPax Web Application Prototype:** [Consultar prototipo web en Figma](https://www.figma.com/proto/xUBTqYXN6DG591Wr9j4njh/Web-Application?node-id=31-4505&p=f&t=yaGOrsZicVQS44O0-1&scaling=min-zoom&content-scaling=fixed&page-id=29%3A2&starting-point-node-id=31%3A4505).

### Repositorios del proyecto

| Producto | Repositorio GitHub | Historial de ramas |
|---|---|---|
| Informe | [VetPax-Report](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Report) | [Branches](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Report/branches) |
| Backend API y pruebas | [VetPax-Backend](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Backend) | [Branches](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Backend/branches) |
| Aplicación web | [VetPax-Web_Application](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Web_Application) | [Branches](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Web_Application/branches) |
| Aplicación móvil | [VetPax-Mobile_Application](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Mobile_Application) | [Branches](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Mobile_Application/branches) |
| Landing Page | [VetPax-Landing_Page](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Landing_Page) | [Branches](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Landing_Page/branches) |

### Enlaces de ejecución y documentación de servicios

- **Landing Page de VetPax:** https://vetpax-landing-page.netlify.app/
- **API REST de VetPax en Railway (dirección configurada en el backend):** https://vetpax-api-production.up.railway.app/
- **Swagger UI (ruta configurada):** https://vetpax-api-production.up.railway.app/swagger/
- **Especificación OpenAPI (ruta configurada):** https://vetpax-api-production.up.railway.app/openapi/v1.json
- **Keycloak:** https://keycloak-production-91a6.up.railway.app/
- **Web Application:** https://vetpax-web-application.netlify.app/
- **Mobil Application:**https://drive.google.com/drive/folders/1N6InfHjUsmTkFHhGUPxsdaAsKK7jIarE?usp=sharing

### Pull requests representativos de integración

- **Backend, PR #9:** [Integración de `feature/deployment`](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Backend/pull/9).
- **Backend, PR #19:** [Integración de `feature/authentication`](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Backend/pull/19).
- **Backend, PR #20:** [Integración de `develop`](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Backend/pull/20).
- **Aplicación web, PR #1:** [Integración de `develop`](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Web_Application/pull/1).
- **Informe, PR #24:** [Integración de `feature/chapter-7`](https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Report/pull/24).