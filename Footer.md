### **Conclusiones**

1. El desarrollo de **VetPax** permitió identificar una oportunidad de diferenciación frente a las soluciones veterinarias existentes. Mientras diversas plataformas del mercado se orientan principalmente a la administración de clínicas, historiales, inventarios y citas, VetPax plantea un enfoque especializado en el **seguimiento clínico y nutricional continuo de mascotas geriátricas o con enfermedades crónicas**, buscando mantener la continuidad del cuidado entre consultas.

2. Las entrevistas realizadas a los segmentos objetivo permitieron identificar necesidades relacionadas con la falta de tiempo, el olvido de citas y medicamentos, la dificultad para mantener información clínica organizada y los problemas de seguimiento entre una consulta y otra. Estos hallazgos respaldan la incorporación de funcionalidades como el historial clínico centralizado, recordatorios, agenda veterinaria, planes nutricionales y seguimiento de tratamientos.

3. A partir del proceso de **Requirements Elicitation & Analysis**, las necesidades identificadas fueron transformadas en **Epic Stories, User Stories y Technical Stories**, acompañadas de criterios de aceptación verificables. Esto permite establecer una relación clara entre las necesidades de los usuarios y las funcionalidades y capacidades técnicas que deberá implementar VetPax.

4. El **Product Backlog** permite organizar y priorizar progresivamente las funcionalidades de VetPax de acuerdo con el valor que aportan a los segmentos objetivo. En este backlog se consideran elementos relacionados con la Landing Page, registro y autenticación, gestión de mascotas, historial clínico, citas, recordatorios, nutrición, gestión de pacientes, gamificación e integraciones técnicas.

5. A nivel arquitectónico, la adopción de una **arquitectura hexagonal** permite separar la lógica principal del dominio de elementos externos como interfaces de usuario, mecanismos de persistencia y servicios de terceros. Esta separación favorece la mantenibilidad de la solución y permite realizar modificaciones tecnológicas con menor impacto sobre las reglas principales del negocio.

6. La utilización de tecnologías y mecanismos como **APIs RESTful, Keycloak, Firebase Cloud Messaging y WebSockets** responde a necesidades específicas de la solución. Keycloak permite gestionar autenticación, autorización y roles; Firebase Cloud Messaging permite enviar notificaciones relacionadas con tratamientos y citas; WebSockets facilita la comunicación en tiempo real; y las APIs REST permiten desacoplar las aplicaciones cliente de los servicios backend.

7. La aplicación de **Domain-Driven Design y EventStorming** permitió analizar las principales capacidades de negocio de VetPax y organizarlas en áreas relacionadas con gestión clínica, citas, tratamientos de medicación, nutrición, gestión de clínicas, adherencia y gamificación, e identidad y acceso. Esta organización proporciona una base para la identificación de Bounded Contexts y la separación de responsabilidades dentro de la arquitectura.

8. En conjunto, los artefactos desarrollados permiten mantener una trazabilidad entre el problema identificado, las necesidades de los usuarios, los requerimientos funcionales, las historias de usuario y las decisiones arquitectónicas. De esta manera, VetPax se plantea como una solución multicanal compuesta por una aplicación móvil para dueños de mascotas, una aplicación web para veterinarias, una Landing Page, servicios backend e integraciones con servicios externos.

### **Bibliografia**

#### Documentos del curso

- Universidad Peruana de Ciencias Aplicadas. (2024). *SI728 Arquitecturas de Software Emergentes - Enunciado del Trabajo Final*. Facultad de Ingeniería, Universidad Peruana de Ciencias Aplicadas.

- Universidad Peruana de Ciencias Aplicadas. (2026). *Rúbrica ABET - 1ASI0728 Arquitecturas de Software Emergentes*. Facultad de Ingeniería, Universidad Peruana de Ciencias Aplicadas.

- Universidad Peruana de Ciencias Aplicadas. (2026). *Rúbrica de Logro - 1ASI0728 Arquitecturas de Software Emergentes*. Facultad de Ingeniería, Universidad Peruana de Ciencias Aplicadas.

#### Competidores

- VetOS. (s.f.). *Software veterinario para gestión de clínicas veterinarias*. Sistema VetOS.

- PetSuite. (s.f.). *Software de gestión para veterinarias*. PetSuite.

- GVET. (s.f.). *Software de gestión para clínicas y hospitales veterinarios*. GVET.

- VetFac. (s.f.). *Software veterinario y facturación electrónica*. VetFac.

- SmartVet360. (s.f.). *Software veterinario en la nube*. SmartVet360.

#### Arquitectura y tecnologías

- Keycloak. (s.f.). *Keycloak Documentation*. Keycloak.

- Google. (s.f.). *Firebase Cloud Messaging Documentation*. Firebase.

- Mozilla Developer Network. (s.f.). *WebSocket API*. MDN Web Docs.

- Richardson, C. (2018). *Microservices Patterns: With Examples in Java*. Manning Publications.

- Evans, E. (2003). *Domain-Driven Design: Tackling Complexity in the Heart of Software*. Addison-Wesley.

- Vernon, V. (2013). *Implementing Domain-Driven Design*. Addison-Wesley.

- Brandolini, A. (s.f.). *EventStorming*. EventStorming.

#### Experiencia de usuario y desarrollo de producto

- Gothelf, J., & Seiden, J. (2021). *Lean UX: Designing Great Products with Agile Teams*. O'Reilly Media.

- Cohn, M. (2004). *User Stories Applied: For Agile Software Development*. Addison-Wesley.

### **Anexo**

- Event Storming: [https://miro.com/app/board/uXjVHk77Zs8=/?share_link_id=766277899100](https://miro.com/app/board/uXjVHk77Zs8=/?share_link_id=766277899100)