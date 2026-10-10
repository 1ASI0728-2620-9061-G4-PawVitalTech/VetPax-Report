<div style="page-break-after: always;"></div>

### **Conclusiones**

1. El desarrollo de **VetPax** permitió identificar una oportunidad de diferenciación frente a las soluciones veterinarias existentes. Mientras diversas plataformas del mercado se orientan principalmente a la administración de clínicas, historiales, inventarios y citas, VetPax plantea un enfoque especializado en el **seguimiento clínico y nutricional continuo de mascotas geriátricas o con enfermedades crónicas**, buscando mantener la continuidad del cuidado entre consultas mediante herramientas digitales que conecten a propietarios y profesionales veterinarios.

2. Las entrevistas realizadas a los segmentos objetivo permitieron identificar necesidades relacionadas con la disponibilidad de tiempo, la organización de controles veterinarios, el acceso a información clínica y las dificultades de seguimiento entre consultas. Estos hallazgos proporcionaron un sustento inicial para incorporar funcionalidades como el historial clínico centralizado, recordatorios, agenda veterinaria, planes nutricionales y seguimiento de tratamientos. Asimismo, permitieron orientar el diseño hacia una distribución clara de responsabilidades: los propietarios consultan la información y registran actividades de cuidado, mientras que los profesionales veterinarios son responsables de registrar y validar las atenciones clínicas y las indicaciones terapéuticas.

3. Los antecedentes internacionales permitieron respaldar la pertinencia de incorporar herramientas digitales para mejorar la organización y continuidad de la atención veterinaria. En Estados Unidos, PetDesk reportó el caso de una clínica veterinaria de San Diego cuya proporción de inasistencias disminuyó del 11 % a menos del 3 % después de implementar herramientas de comunicación y recordatorios digitales (PetDesk, s. f.). Asimismo, Silva (2023), en una investigación realizada en Portugal, identificó una asociación entre el uso de recordatorios digitales y la asistencia a consultas de revacunación canina, registrando 54 asistencias en los grupos que recibieron mensajes frente a 4 en el grupo de control. Estos antecedentes respaldan el enfoque de VetPax, aunque sus resultados no garantizan un impacto equivalente en el contexto peruano. Por ello, será necesario evaluar posteriormente indicadores como la asistencia a controles, el uso de recordatorios y la consulta del historial clínico.

4. A partir del proceso de **Requirements Elicitation & Analysis**, las necesidades identificadas fueron transformadas en **Epic Stories, User Stories y Technical Stories**, acompañadas de criterios de aceptación verificables. Esta especificación permitió establecer una relación entre los problemas identificados, las necesidades de los segmentos objetivo y las funcionalidades y capacidades técnicas propuestas. Asimismo, el Product Backlog proporciona una base para organizar y priorizar progresivamente los elementos del producto según su valor de negocio y sus dependencias.

5. A nivel arquitectónico, la selección de **Hexagonal Architecture** permite organizar la solución mediante una separación entre las reglas del dominio, los casos de uso y las dependencias de infraestructura. La utilización de Ports and Adapters favorece la mantenibilidad, ya que permite encapsular mecanismos de persistencia, servicios externos y tecnologías de comunicación sin introducir dependencias directas de estos elementos en las reglas principales del negocio. Esta decisión resulta especialmente relevante para una plataforma que integra información clínica, recordatorios, gestión de citas y servicios de terceros.

6. La aplicación de **Domain-Driven Design y EventStorming** permitió analizar las capacidades principales del negocio e identificar siete bounded contexts: **Pet & Clinical Care, Appointment Management, Medication Treatment, Nutrition Management, Clinic Management, Adherence & Gamification e Identity & Access Management**. Su organización dentro de un único backend modular responde al alcance inicial de VetPax, al reducir la complejidad operativa frente a una arquitectura de microservicios. Cada contexto conserva sus propias responsabilidades, reglas de negocio y contratos de comunicación, mientras que la base de datos centralizada contempla una separación lógica y propiedad de datos por módulo. Esta organización favorece la cohesión y mantenibilidad, aunque no proporciona escalamiento ni despliegue independiente de cada bounded context.

7. Las decisiones relacionadas con **APIs RESTful, Keycloak, Firebase Cloud Messaging y WebSockets** responden a diferentes necesidades funcionales y atributos de calidad. Las APIs RESTful proporcionan los mecanismos principales de consulta y registro; Keycloak permite centralizar la gestión de identidad y autenticación; Firebase Cloud Messaging facilita la entrega de notificaciones relacionadas con citas, tratamientos y actividades de cuidado; y WebSockets permite comunicar actualizaciones relevantes a los clientes autorizados conectados. La separación de estas responsabilidades contribuye a establecer contratos de integración claros y evitar acoplamientos innecesarios entre los componentes de la solución.

8. El análisis de los atributos de calidad permitió reconocer que una arquitectura con un único backend modular y una base de datos centralizada presenta ventajas de simplicidad inicial, pero también dependencias compartidas que deben ser consideradas. En particular, la indisponibilidad de la persistencia puede afectar simultáneamente a diversas funcionalidades de VetPax. Por ello, la arquitectura propuesta contempla mecanismos de monitoreo, respaldos, recuperación y posibles estrategias de redundancia, sujetos a las capacidades de la infraestructura seleccionada. La efectividad de estas decisiones deberá comprobarse posteriormente mediante pruebas de disponibilidad, rendimiento y recuperación, utilizando indicadores como RTO y RPO.

9. El desarrollo de la propuesta de **Solution UX Design** permitió establecer una experiencia diferenciada para los segmentos objetivo mediante una aplicación móvil orientada a propietarios y una aplicación web destinada a profesionales y administradores veterinarios. Las Style Guidelines, la arquitectura de información, los wireframes, mock-ups, wireflows, User Flow Diagrams y prototipos interactivos proporcionan una referencia visual y funcional para la implementación de los productos digitales, manteniendo coherencia entre las funcionalidades propuestas y las responsabilidades definidas en los requisitos.

10. En conjunto, los artefactos elaborados permitieron establecer una trazabilidad entre la problemática identificada, las necesidades de los usuarios, los requisitos, las historias de usuario, las decisiones arquitectónicas y el diseño de las interfaces. **VetPax constituye una propuesta de solución digital multicanal** orientada a facilitar la continuidad del seguimiento veterinario mediante una aplicación móvil, una aplicación web, una Landing Page y servicios backend integrados. Su efectividad deberá validarse en etapas posteriores mediante pruebas funcionales, evaluaciones de calidad y experiencias de uso con participantes de los segmentos objetivo.

---

### **Bibliografía**

#### **Documentos del curso**

- Universidad Peruana de Ciencias Aplicadas. (2024). *SI728 Arquitecturas de Software Emergentes - Enunciado del Trabajo Final*. Facultad de Ingeniería, Universidad Peruana de Ciencias Aplicadas.

- Universidad Peruana de Ciencias Aplicadas. (2026). *Rúbrica ABET - 1ASI0728 Arquitecturas de Software Emergentes*. Facultad de Ingeniería, Universidad Peruana de Ciencias Aplicadas.

- Universidad Peruana de Ciencias Aplicadas. (2026). *Rúbrica de Logro - 1ASI0728 Arquitecturas de Software Emergentes*. Facultad de Ingeniería, Universidad Peruana de Ciencias Aplicadas.

#### **Competidores**

- VetOS. (s. f.). *Software veterinario para gestión de clínicas veterinarias*. Sistema VetOS.

- PetSuite. (s. f.). *Software de gestión para veterinarias*. PetSuite.

- GVET. (s. f.). *Software de gestión para clínicas y hospitales veterinarios*. GVET.

- VetFac. (s. f.). *Software veterinario y facturación electrónica*. VetFac.

- SmartVet360. (s. f.). *Software veterinario en la nube*. SmartVet360.

#### **Antecedentes internacionales y evidencia de soluciones veterinarias digitales**

- PetDesk. (s. f.). *Increased revenue by over $225K with PetDesk*. https://petdesk.com/resources/increased-revenue-with-petdesk

- Silva, B. I. S. (2023). *O potencial das ferramentas digitais no incentivo ao cumprimento de programas vacinais por detentores de cães* [Disertación de maestría, Universidade de Lisboa]. Repositório da Universidade de Lisboa. https://hdl.handle.net/10400.5/28425

#### **Arquitectura y tecnologías**

- Keycloak. (s. f.). *Keycloak Documentation*. https://www.keycloak.org/documentation

- Google. (s. f.). *Firebase Cloud Messaging*. Firebase Documentation. https://firebase.google.com/docs/cloud-messaging

- Mozilla. (s. f.). *WebSocket API (WebSockets)*. MDN Web Docs. https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API

- Richardson, C. (2018). *Microservices patterns: With examples in Java*. Manning Publications.

- Evans, E. (2003). *Domain-driven design: Tackling complexity in the heart of software*. Addison-Wesley.

- Vernon, V. (2013). *Implementing domain-driven design*. Addison-Wesley.

- Brandolini, A. (s. f.). *EventStorming*. https://www.eventstorming.com/

#### **Experiencia de usuario y desarrollo de producto**

- Gothelf, J., & Seiden, J. (2021). *Lean UX: Designing great products with agile teams*. O'Reilly Media.

- Cohn, M. (2004). *User stories applied: For agile software development*. Addison-Wesley.

---

### **Anexo**

#### **EventStorming**

- **EventStorming de VetPax:** [Consultar tablero en Miro](https://miro.com/app/board/uXjVHk77Zs8=/?share_link_id=766277899100)

#### **Prototipos de Figma**

- **VetPax Mobile Application Prototype:** [Consultar prototipo móvil en Figma](https://www.figma.com/proto/w9edhFA6VCAvT7Rl3wKKe2/Mobil-Application?node-id=22-2411&t=CR6IkEqjYgPmg0Kf-1&scaling=min-zoom&content-scaling=fixed&page-id=20%3A2&starting-point-node-id=22%3A2475)

- **VetPax Web Application Prototype:** [Consultar prototipo web en Figma](https://www.figma.com/proto/xUBTqYXN6DG591Wr9j4njh/Web-Application?node-id=31-4505&p=f&t=yaGOrsZicVQS44O0-1&scaling=min-zoom&content-scaling=fixed&page-id=29%3A2&starting-point-node-id=31%3A4505)