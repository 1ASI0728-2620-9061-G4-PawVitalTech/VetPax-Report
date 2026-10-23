# Capítulo VII: Product Implementation, Validation & Deployment

En este capítulo se describe la configuración del entorno de desarrollo, el control de versiones, las convenciones de programación y el proceso previsto de implementación, pruebas, validación y despliegue de **VetPax**, producto digital desarrollado por **PawVital Tech** para apoyar el seguimiento clínico y nutricional de mascotas geriátricas o con enfermedades crónicas.

La solución está compuesta por una aplicación móvil desarrollada con **Flutter y Dart**, una aplicación web para el segmento veterinario desarrollada con **Angular 21**, una **Landing Page** y un backend REST desarrollado con **C# y ASP.NET Core sobre .NET 10**. El backend sigue una aproximación de **Domain-Driven Design (DDD)**, arquitectura **hexagonal** y **monolito modular**, de acuerdo con el diseño estratégico y táctico presentado en los capítulos IV y V.

El contenido distingue entre tecnologías y funcionalidades cuyo uso o avance ha sido informado, decisiones arquitectónicas todavía propuestas y evidencias por incorporar. La documentación por sprint se completará con los registros de planificación y ejecución reales; no se asignan historias ni contribuciones a una iteración sin el Sprint Backlog y el historial correspondiente.

## 7.1. Software Configuration Management

En esta sección se establecen las herramientas y convenciones consideradas para gestionar los elementos de software de VetPax. La gestión de configuración busca mantener la coherencia entre sus productos digitales, favorecer el trabajo colaborativo y conservar la trazabilidad de los cambios realizados en el código fuente, la documentación, los servicios y las pruebas.

Se presentan el entorno de desarrollo de los productos, la estrategia de control de versiones, los estándares de programación y la configuración conocida para ejecutar el backend en un entorno local. Los procedimientos de despliegue de los demás productos se documentarán cuando existan configuraciones verificables.

### 7.1.1. Software Development Environment Configuration

A continuación se detalla la configuración tecnológica conocida de los productos de software de VetPax. Las herramientas se organizan según su propósito en el ciclo de desarrollo. Se identifican explícitamente los elementos utilizados en el backend y los datos que todavía requieren confirmación en las aplicaciones cliente y en la infraestructura de despliegue.

**Backend Web Services**

El backend de VetPax se desarrolla en **C# con ASP.NET Core Web API y .NET 10**, utilizando una organización por capas y responsabilidades. La solución contiene los siguientes proyectos de producción y uno de pruebas:

| Proyecto | Responsabilidad |
|---|---|
| `VetPax.Domain` | Agregados, entidades, Value Objects, fábricas, políticas, eventos y servicios de dominio. |
| `VetPax.Application` | Commands, Queries, Handlers y puertos de aplicación. |
| `VetPax.Infrastructure` | Persistencia con EF Core y MySQL, repositorios, Unit of Work y adaptadores externos. |
| `VetPax.Api` | Controllers, DTOs de solicitud y respuesta, Swagger/OpenAPI y configuración de dependencias. |
| `VetPax.Tests` | Pruebas unitarias, de integración y escenarios de aceptación BDD. |

Las herramientas y bibliotecas documentadas para este producto son:

| Herramienta | Versión / referencia conocida | Propósito en VetPax | Enlace oficial |
|---|---|---|---|
| JetBrains Rider | Versión exacta no indicada | Entorno de desarrollo del backend y ejecución de pruebas. | https://www.jetbrains.com/rider/ |
| .NET SDK / ASP.NET Core Web API | .NET 10 | Implementación y ejecución de los servicios HTTP. | https://dotnet.microsoft.com/ |
| Entity Framework Core | 9 | Acceso a datos y gestión de migraciones. | https://learn.microsoft.com/ef/core/ |
| Pomelo.EntityFrameworkCore.MySql | 9.x | Proveedor de EF Core para MySQL. | https://github.com/PomeloFoundation/Pomelo.EntityFrameworkCore.MySql |
| MySQL | 8.x | Persistencia relacional de la información de negocio. | https://dev.mysql.com/ |
| Swagger UI / OpenAPI | Versión no indicada | Documentación de contratos y ejecución manual de solicitudes HTTP. | https://swagger.io/ |
| xUnit | Versión no indicada | Pruebas unitarias del backend, según el avance técnico reportado. | https://xunit.net/ |
| NSubstitute | Versión no indicada | Sustitución de dependencias durante pruebas. | https://nsubstitute.github.io/ |
| Reqnroll y Gherkin | Versión no indicada | Especificación y automatización de escenarios BDD. | https://reqnroll.net/ |
| WebApplicationFactory | Versión no indicada | Ejecución de solicitudes HTTP sobre una instancia de prueba de la API. | https://learn.microsoft.com/aspnet/core/test/integration-tests |
| Git | Versión no indicada | Control local de versiones del código fuente. | https://git-scm.com/ |
| GitHub | Plataforma | Repositorios y colaboración de desarrollo. | https://github.com/ |



**Web Application**

La aplicación web está dirigida a profesionales veterinarios y administradores de clínicas. Se utiliza **Angular 21** para desarrollar la experiencia de gestión de pacientes, citas y consulta de información clínica contemplada en los requisitos y prototipos del capítulo VI.

| Herramienta | Versión / referencia conocida | Propósito | Enlace oficial |
|---|---|---|---|
| Angular | 21 | Framework de la aplicación web. | https://angular.dev/ |
| TypeScript | Versión del proyecto por confirmar | Lenguaje utilizado por Angular. | https://www.typescriptlang.org/ |
| HTML y CSS | Estándares web | Estructuración y presentación de interfaces. | https://developer.mozilla.org/ |
| Biblioteca de componentes | [PENDIENTE: CONFIRMAR] | Componentes visuales de la aplicación web. | [PENDIENTE: ENLACE] |
| IDE y herramientas de pruebas | [PENDIENTE: CONFIRMAR] | Desarrollo y verificación de la aplicación web. | [PENDIENTE: ENLACE] |

**Mobile Application**

La aplicación móvil está orientada a propietarios de mascotas y utiliza **Flutter con Dart**. Los flujos funcionales se encuentran definidos en el capítulo VI; su implementación y el estado de sus pantallas deben acreditarse posteriormente mediante el repositorio y evidencias de ejecución.

| Herramienta | Versión / referencia conocida | Propósito | Enlace oficial |
|---|---|---|---|
| Flutter | Versión no indicada | Framework de la aplicación móvil. | https://flutter.dev/ |
| Dart | Versión no indicada | Lenguaje de programación móvil. | https://dart.dev/ |
| IDE, emuladores y herramientas de pruebas | [PENDIENTE: CONFIRMAR] | Edición, ejecución y verificación de la aplicación móvil. | [PENDIENTE: ENLACE] |

**Gestión del proyecto, análisis y documentación**

| Herramienta | Propósito | Estado de información | Enlace oficial |
|---|---|---|---|
| GitHub | Versionamiento del informe y proyectos. | Repositorio del informe identificado; URLs de código pendientes. | https://github.com/ |
| Figma | Wireframes, mock-ups, user flows y prototipos. | Documentado en el capítulo VI. | https://www.figma.com/ |
| UXPressia | User Personas, Empathy Maps e Impact Maps. | Considerado en los artefactos de requisitos. | https://uxpressia.com/ |
| Miro | Diagramación y trabajo colaborativo de análisis. | Considerado en los capítulos anteriores. | https://miro.com/ |
| Structurizr | Diagramas de arquitectura C4. | Considerado en el diseño arquitectónico. | https://structurizr.com/ |
| Herramienta de gestión de Product/Sprint Backlog | Priorización, tareas y estados del sprint. | [PENDIENTE: CONFIRMAR HERRAMIENTA Y BOARD] | [PENDIENTE: URL] |
| Proveedor de despliegue | Publicación de los productos digitales. | [PENDIENTE: SELECCIÓN Y CONFIGURACIÓN] | [PENDIENTE: URL] |

Las versiones y configuraciones que todavía no figuran en la información disponible se incorporarán cuando se obtengan los archivos de configuración de cada proyecto y las evidencias de su ejecución.

### 7.1.2. Source Code Management

El almacenamiento y control de versiones de VetPax se plantea sobre Git y GitHub, con la finalidad de registrar modificaciones, facilitar el desarrollo colaborativo y conservar la trazabilidad entre requisitos, cambios de código y versiones del producto.

La organización del equipo y el repositorio de documentación ya están identificados:

- **Organización:** https://github.com/1ASI0728-2620-9061-G4-PawVitalTech
- **Repositorio del informe:** https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Report.git

| Producto digital / artefacto | Tecnología | Repositorio |
|---|---|---|
| Informe del proyecto | Markdown | https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Report.git |
| Backend Web Services y pruebas | C# / ASP.NET Core / .NET 10 | https://github.com/1ASI0728-2620-9061-G4-PawVitalTech/VetPax-Backend.git |
| Web Application | Angular 21 | [PENDIENTE: URL REAL] |
| Mobile Application | Flutter / Dart | [PENDIENTE: URL REAL] |
| Landing Page | Tecnología y repositorio por confirmar | [PENDIENTE: URL REAL] |

El proyecto de pruebas `VetPax.Tests`, incluidos los archivos `.feature` y sus definiciones de pasos, deberá quedar accesible en el repositorio del backend, conforme a lo exigido por el enunciado.

**GitFlow Workflow**

El curso establece la utilización de GitFlow. Para su aplicación se consideran las siguientes ramas y propósitos. Esta tabla describe la **convención de trabajo que debe adoptarse o verificarse**, no una relación de ramas cuya existencia ya haya sido comprobada.

| Rama | Propósito |
|---|---|
| `main` | Mantener versiones estables y publicables. |
| `develop` | Integrar funcionalidades preparadas para la siguiente versión. |
| `feature/*` | Desarrollar funcionalidades de manera aislada. |
| `release/*` | Preparar una versión para publicación. |
| `hotfix/*` | Corregir defectos urgentes de una versión estable. |

Como nomenclatura propuesta para funcionalidades se utilizará `feature/<story-id>-<description>`, por ejemplo `feature/us01-register-pet`. Los nombres concretos de ramas, Pull Requests y fusiones deberán contrastarse con los repositorios reales.

**Conventional Commits y Semantic Versioning**

Se propone utilizar Conventional Commits para que los mensajes permitan distinguir funcionalidades, correcciones, pruebas, documentación y mantenimiento. Los siguientes mensajes son **ejemplos de formato**, no commits acreditados:

| Tipo | Uso | Ejemplo ilustrativo |
|---|---|---|
| `feat` | Nueva funcionalidad | `feat: add pet registration` |
| `fix` | Corrección de comportamiento | `fix: validate clinical record access` |
| `test` | Pruebas | `test: add clinical history scenarios` |
| `docs` | Documentación | `docs: update API contracts` |
| `refactor` | Reorganización interna | `refactor: isolate persistence adapters` |
| `chore` | Configuración y mantenimiento | `chore: update development settings` |

Para las publicaciones se adoptará el formato `MAJOR.MINOR.PATCH` de Semantic Versioning: cambios incompatibles, nuevas capacidades compatibles y correcciones compatibles, respectivamente. Los identificadores de las versiones efectivamente publicadas se registrarán cuando existan releases.

**[PENDIENTE: capturas de las ramas utilizadas, enlaces a Pull Requests, historial de commits y versiones publicadas de cada repositorio.]**

### 7.1.3. Source Code Style Guide & Conventions

Las convenciones de programación de VetPax buscan mantener un código legible y consistente entre los productos digitales. Se utiliza la nomenclatura en **inglés** para identificadores técnicos, conforme al enunciado del curso. Se diferencian los estándares correspondientes a C#, TypeScript/Angular, Dart/Flutter y Gherkin.

**C# / ASP.NET Core**

El backend se encuentra organizado en los proyectos `VetPax.Domain`, `VetPax.Application`, `VetPax.Infrastructure` y `VetPax.Api`. Esta separación permite mantener las reglas de negocio independientes de las dependencias de infraestructura y exponer los casos de uso mediante contratos HTTP.

| Elemento | Convención | Ejemplo ilustrativo |
|---|---|---|
| Clases, métodos y propiedades públicas | PascalCase | `RegisterPetCommand`, `HandleAsync()` |
| Interfaces | Prefijo `I` y PascalCase | `IPetRepository` |
| Variables y parámetros | camelCase | `petId`, `request` |
| Campos privados | Prefijo `_` y camelCase | `_petRepository` |
| Tipos Command / Query | Sufijos `Command` / `Query` | `RegisterPetCommand` |
| Handlers | Sufijo `Handler` | `RegisterPetCommandHandler` |
| Controllers | Sufijo `Controller` | `PetsController` |
| Contratos de entrada y salida | DTOs con nombres descriptivos | `RegisterPetRequest` |
| Namespaces | Correspondencia con capas y dominio | `VetPax.Application` |

Los ejemplos anteriores describen un patrón de estilo y no constituyen una lista verificada de clases del repositorio.

Se consideran además las siguientes reglas: la capa `Domain` no dependerá de EF Core ni de detalles de los servicios externos; el acceso a datos se realizará mediante abstracciones y adaptadores; la coordinación de casos de uso permanecerá en `Application`; y los controladores HTTP se limitarán a las responsabilidades de interfaz. Cuando corresponda, se utilizarán `async/await` y `CancellationToken` en las operaciones asíncronas.

**TypeScript / Angular 21**

| Elemento | Convención | Ejemplo ilustrativo |
|---|---|---|
| Clases, interfaces y componentes | PascalCase | `PatientListComponent` |
| Variables y métodos | camelCase | `loadPatients()` |
| Archivos | kebab-case | `patient-list.component.ts` |
| Servicios | Nombre descriptivo y sufijo `Service` cuando corresponda | `PatientService` |
| Rutas de navegación | kebab-case | `/clinical-records` |

Las interfaces se organizarán mediante componentes reutilizables. La comunicación HTTP con el backend deberá mantener correspondencia con los endpoints y contratos reales de la API y evitar la incorporación de campos o comportamientos que no estén implementados.

**Dart / Flutter**

| Elemento | Convención | Ejemplo ilustrativo |
|---|---|---|
| Clases y widgets | UpperCamelCase | `PetDetailScreen` |
| Variables y métodos | lowerCamelCase | `loadClinicalHistory()` |
| Archivos | snake_case | `pet_detail_screen.dart` |
| Miembros privados | Prefijo `_` | `_loadPets()` |
| Constantes | lowerCamelCase | `defaultPageSize` |

El desarrollo móvil procurará mantener separadas la composición de widgets, las operaciones de aplicación y el acceso a servicios externos, en coherencia con los flujos definidos en el capítulo VI.

**Gherkin y archivos de pruebas**

Las pruebas de aceptación del backend utilizan Reqnroll y archivos `.feature`. La especificación actual incluye `RegisterPet.feature` y `GetClinicalHistory.feature`, vinculados con US01 y US02, además de definiciones de pasos en C#.

Los archivos `.feature` deben contener escenarios verificables que describan condiciones, acciones y resultados. En los materiales técnicos disponibles se señala que los escenarios existentes utilizan **`# language: es` y textos en español**. Esta diferencia con el requisito de nomenclatura en inglés debe revisarse y resolverse con el equipo; no se declara corregida.

La nomenclatura de clases de prueba, las dependencias y el runner de los escenarios BDD deberán verificarse en el proyecto `VetPax.Tests` antes de presentar una guía de estilo definitiva.

**Endpoints REST**

La API utiliza rutas con versión `/api/v1/` y recursos definidos en inglés. Los verbos HTTP indican la operación correspondiente. Los contratos conocidos del bounded context `PetClinicalCare` incluyen los siguientes recursos:

| Método | Ruta | Propósito |
|---|---|---|
| POST | `/api/v1/pets` | Registrar una mascota. |
| GET | `/api/v1/pets/{petId}` | Consultar una mascota. |
| GET | `/api/v1/pets/{petId}/clinical-records` | Consultar el historial clínico. |
| POST | `/api/v1/pets/{petId}/clinical-records` | Registrar una atención clínica; temporalmente restringido. |
| GET | `/api/v1/pets/{petId}/evolution` | Consultar la evolución clínica; temporalmente restringido. |

Las respuestas HTTP deberán utilizar códigos adecuados al resultado de las operaciones y respetar el control de acceso. Los encabezados `X-Dev-*` utilizados en Development son auxiliares de prueba y **no constituyen autenticación real**.

**Git y control de versiones**

El código deberá versionarse en GitHub siguiendo las convenciones de ramas, mensajes de commits y versionamiento establecidas en la sección 7.1.2. La verificación del cumplimiento de estas prácticas se realizará a partir del historial real de cada repositorio.

### 7.1.4. Software Deployment Configuration

Esta sección explica la configuración conocida para ejecutar el backend de VetPax y documenta los elementos necesarios para alcanzar el despliegue de los productos digitales. El diseño de referencia se encuentra en el **Deployment Diagram de la sección 4.3.4** del informe y deberá actualizarse cuando se confirme la infraestructura efectivamente utilizada.

**Arquitectura de despliegue propuesta**

| Producto / componente | Tecnología | Entorno previsto o estado de información |
|---|---|---|
| Landing Page | [PENDIENTE: CONFIRMAR IMPLEMENTACIÓN] | [PENDIENTE: HOSTING Y URL] |
| Web Application | Angular 21 | [PENDIENTE: HOSTING Y URL] |
| Mobile Application | Flutter / Dart | [PENDIENTE: MÉTODO DE DISTRIBUCIÓN] |
| Backend API | ASP.NET Core / .NET 10 | Ejecución local documentada; [PENDIENTE: CLOUD Y URL] |
| Database | MySQL 8.x | Bases locales `vetpax_db` y `vetpax_test_db`; [PENDIENTE: BASE CLOUD] |
| Identity Provider | Keycloak, según arquitectura objetivo | [PENDIENTE: INTEGRACIÓN REAL] |
| Push Notifications | Firebase Cloud Messaging, según arquitectura objetivo | [PENDIENTE: INTEGRACIÓN REAL] |
| External Calendar | Proveedor externo por definir | [PENDIENTE: INTEGRACIÓN REAL] |

**Configuración local del backend**

El backend cuenta con una configuración local de persistencia MySQL. Las migraciones de EF Core se almacenan en `src/VetPax.Infrastructure/Persistence/Migrations/`. El contexto técnico indica que, en el entorno de Development, se utiliza `Database.MigrateAsync()` para aplicar migraciones pendientes al iniciar la API. Las contraseñas se gestionan mediante .NET User Secrets o variables de entorno y no deben incorporarse al repositorio.

Como referencia para reproducir el entorno desde la raíz del proyecto, se dispone de los siguientes comandos, cuya ejecución supone que .NET SDK, la herramienta `dotnet ef` y MySQL estén configurados:

```bash
git clone <URL_REAL_REPOSITORIO>
cd VetPax-Backend
dotnet restore
dotnet build
dotnet ef database update --project src/VetPax.Infrastructure --startup-project src/VetPax.Api
dotnet run --project src/VetPax.Api --launch-profile https
dotnet test tests/VetPax.Tests/VetPax.Tests.csproj
```

El comando de migración explícita se presenta como mecanismo de preparación del entorno; en Development, la aplicación también tiene configurada la aplicación automática de migraciones pendientes. La disponibilidad de la herramienta `dotnet ef` y los nombres exactos de perfiles se verificarán con los archivos del repositorio.

La documentación Swagger se consulta localmente desde la ruta `https://localhost:<PUERTO>/swagger`, donde el puerto depende de la configuración real del proyecto. Esta dirección es **local** y no equivale a una URL pública de despliegue.

**[PENDIENTE: URL del repositorio backend, capturas del entorno local y de Swagger, proveedor cloud, configuración de hosting, base de datos administrada, procedimiento de publicación, SSL, respaldos, CI/CD y Deployment Diagram actualizado.]**

## 7.2. Solution Implementation

La implementación de VetPax se documentará por sprint mediante los elementos seleccionados del Product Backlog. Para cada iteración se registrarán la planificación, el Sprint Backlog, los commits, las pruebas, la ejecución de las funcionalidades, la documentación de servicios, el despliegue y las evidencias de colaboración del equipo.

A la fecha de la información proporcionada, se cuenta con un avance técnico documentado en el bounded context **PetClinicalCare**. Los demás bounded contexts forman parte del diseño de la solución, pero no deben considerarse implementados sin evidencia de sus respectivos proyectos y casos de uso.

**Estado técnico conocido del backend, todavía sin atribuir a un sprint específico:**

| Elemento | Avance informado | Limitación actual |
|---|---|---|
| `PetClinicalCare` | Capas Domain, Application, Infrastructure y Api; persistencia y endpoints REST. | Resta completar IAM y la autorización clínica integral. |
| Registro de mascota — US01 / TS01 | Endpoint `POST /api/v1/pets`, respuesta `201 Created` verificada en Swagger, según el contexto técnico. | [PENDIENTE: CAPTURA, COMMIT Y SPRINT] |
| Consulta de mascota — TS01 | Endpoint `GET /api/v1/pets/{petId}`, respuestas `200`, `403` y `404` verificadas en Swagger, según el contexto técnico. | [PENDIENTE: CAPTURA, COMMIT Y SPRINT] |
| Consulta de historial — US02 / TS02 | Endpoint de historial con orden cronológico y respuesta para historial vacío, según el contexto técnico. | Autorización provisional en Development; [PENDIENTE: EVIDENCIA] |
| Registro clínico — US03 / TS02 | Controller y caso de uso existentes. | Operación temporalmente bloqueada con `403` por falta de autorización veterinaria real. |
| Evolución clínica — US11 / TS08 | Controller y caso de uso existentes. | Operación temporalmente bloqueada con `403` por falta de autorización veterinaria real. |
| Persistencia | MySQL y migraciones EF Core en entorno local. | [PENDIENTE: EVIDENCIA Y DESPLIEGUE CLOUD] |
| Pruebas | Se reportan 6 unitarias, 3 integraciones MySQL y 4 escenarios BDD. | Se requieren salidas finales, capturas, runner confirmado y commits. |

La información anterior resume el estado del desarrollo conocido y **no equivale a un Sprint Backlog cerrado ni permite asignar esos avances al Sprint 1**. Dicha relación se incorporará al contar con las fechas, el tablero y el historial real de trabajo.

### 7.2.1. Sprint 1

Esta sección documentará la primera iteración del proceso de desarrollo de VetPax. El alcance, las historias seleccionadas, las estimaciones y los resultados deberán registrarse con base en los acuerdos y actividades efectivamente realizadas por el equipo.

#### 7.2.1.1. Sprint Planning 1

El Sprint Planning tiene como finalidad establecer el objetivo de la iteración y seleccionar las User Stories y Technical Stories que el equipo se compromete a desarrollar. La planificación deberá considerar el valor de negocio del Product Backlog y la capacidad disponible.

| Campo | Registro |
|---|---|
| Sprint # | Sprint 1 |
| Date | [PENDIENTE: FECHA] |
| Time | [PENDIENTE: HORA] |
| Location | [PENDIENTE: MODALIDAD O LUGAR] |
| Prepared By | [PENDIENTE: RESPONSABLE] |
| Attendees | [PENDIENTE: PARTICIPANTES] |
| Sprint 0 Review Summary | No aplica: primer sprint. |
| Sprint 0 Retrospective Summary | No aplica: primer sprint. |
| Sprint 1 Goal | [PENDIENTE: OBJETIVO Y MÉTRICA] |
| Sprint 1 Velocity | [PENDIENTE: CAPACIDAD ESTIMADA EN STORY POINTS] |
| Sum of Story Points | [PENDIENTE: SUMA DE HISTORIAS SELECCIONADAS] |

**[PENDIENTE: acta/acuerdos de planificación y relación real de historias comprometidas.]**

#### 7.2.1.2. Sprint Backlog 1

El Sprint Backlog reúne los elementos seleccionados para el Sprint 1 y sus Work-items. La tabla deberá indicar el esfuerzo estimado, los responsables y los estados reales de cada tarea, además del enlace público y una captura del tablero de seguimiento.

| User Story ID | User Story Title | Work-item ID | Work-item Title | Description | Estimation (Hours) | Assigned To | Status |
|---|---|---|---|---|---|---|---|
| [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] |

**[PENDIENTE: URL PÚBLICA DEL BOARD Y CAPTURA DEL SPRINT BACKLOG.]**

#### 7.2.1.3. Development Evidence for Sprint Review

Esta sección registrará las funcionalidades implementadas durante el Sprint 1 y los commits que permiten comprobar su incorporación a los repositorios de los productos digitales. El avance conocido del backend `PetClinicalCare` se asociará a este sprint únicamente si el historial y la planificación respaldan dicha atribución.

| Repository | Branch | Commit ID | Commit Message | Commit Message Body | Committed on (Date) |
|---|---|---|---|---|---|
| [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] |

**[PENDIENTE: URL DE CADA REPOSITORIO, COMMITS REALES Y EVIDENCIAS DEL CÓDIGO DEL SPRINT.]**

#### 7.2.1.4. Testing Suite Evidence for Sprint Review

Las pruebas de los Web Services deberán mostrar la correspondencia entre las funcionalidades comprometidas, los comportamientos verificados y los resultados de ejecución. Para VetPax se reporta la creación de seis pruebas unitarias, tres pruebas de integración con MySQL y cuatro escenarios de aceptación BDD asociados inicialmente a US01 y US02; estas cifras describen el avance informado y **no son evidencia consolidada de su ejecución en el Sprint 1**.

| Tipo | Avance técnico informado | Elementos de evidencia faltantes |
|---|---|---|
| Unit Tests | 6 pruebas de dominio y handlers; se reportaron aprobadas. | [PENDIENTE: CLASES/MÉTODOS, CAPTURA O LOG, COMMIT Y ASOCIACIÓN AL SPRINT] |
| Integration Tests | 3 pruebas MySQL para US01/US02; se reportaron aprobadas. | [PENDIENTE: LOG, BASE DE PRUEBAS, COMMIT Y ASOCIACIÓN AL SPRINT] |
| Acceptance Tests / BDD | 4 escenarios en `RegisterPet.feature` y `GetClinicalHistory.feature`; la ejecución BDD se reportó resuelta. | [PENDIENTE: RESULTADO FINAL, STEPS, RUNNER EFECTIVO, COMMIT Y ASOCIACIÓN AL SPRINT] |

En las pruebas BDD se utilizan archivos `.feature` y definiciones de pasos en C#. El contexto técnico también indica que se incorporó un `ApiAssemblyMarker` público para facilitar la referencia al ensamblado de la API desde `WebApplicationFactory`.

**Relación de pruebas del Sprint 1**

| Test ID | Tipo de prueba | Clase / Feature | User Story relacionada | Resultado acreditado | Evidencia |
|---|---|---|---|---|---|
| [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] |

**Commits de pruebas**

| Repository | Branch | Commit ID | Commit Message | Commit Message Body | Committed on (Date) |
|---|---|---|---|---|---|
| [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] |

**[PENDIENTE: CAPTURAS DE RIDER TEST RUNNER, SALIDA FINAL DE `dotnet test`, CONTENIDO DE `.feature`/STEPS, RUNNER BDD Y COMMITS.]**

#### 7.2.1.5. Execution Evidence for Sprint Review

En esta sección se incorporarán capturas y un video que demuestre el funcionamiento de las aplicaciones y servicios incluidos en el Sprint 1. Las verificaciones de Swagger pueden demostrar solicitudes y respuestas del backend, pero **no reemplazan las capturas de las aplicaciones web y móvil ni la demostración de navegación del producto**.

El contexto técnico indica que existen operaciones de registro y consulta de mascota verificadas localmente en Swagger. Las operaciones veterinarias de registro clínico y evolución están temporalmente bloqueadas y no deben presentarse como flujos funcionales autorizados.

**[PENDIENTE: CAPTURAS DE PANTALLAS REALMENTE IMPLEMENTADAS, EVIDENCIAS SWAGGER CORRESPONDIENTES AL SPRINT Y URL DEL VIDEO DEMOSTRATIVO.]**

#### 7.2.1.6. Services Documentation Evidence for Sprint Review

La documentación de servicios se realizará mediante OpenAPI/Swagger, indicando para cada endpoint implementado el método HTTP, la ruta, los parámetros de entrada y salida, los códigos de respuesta, ejemplos de uso y evidencias de interacción. La siguiente tabla presenta los **endpoints conocidos actualmente** en `PetClinicalCare`; su adscripción al Sprint 1 queda por comprobar.

| Método | Endpoint | US / TS | Comportamiento documentado | Estado / limitación |
|---|---|---|---|---|
| POST | `/api/v1/pets` | US01 / TS01 | Registra la mascota, abre un historial vacío y devuelve `201 Created`. | Probado en Swagger según avance técnico; [PENDIENTE: CAPTURA Y COMMIT]. |
| GET | `/api/v1/pets/{petId}` | TS01 | Consulta la mascota; se reportan `200`, `403` y `404`. | Verificado en Swagger según avance técnico; [PENDIENTE: CAPTURA Y COMMIT]. |
| GET | `/api/v1/pets/{petId}/clinical-records` | US02 / TS02 | Consulta historial ordenado y representa el historial vacío. | Autorización provisional; [PENDIENTE: CAPTURA Y COMMIT]. |
| POST | `/api/v1/pets/{petId}/clinical-records` | US03 / TS02 | Controller y caso de uso de registro clínico. | Temporalmente devuelve `403`; falta autorización veterinaria real. |
| GET | `/api/v1/pets/{petId}/evolution` | US11 / TS08 | Controller y caso de uso de evolución clínica. | Temporalmente devuelve `403`; falta autorización veterinaria real. |

En Development se utilizan temporalmente los encabezados `X-Dev-Owner-Id`, `X-Dev-User-Id` y `X-Dev-Clinic-Id` para facilitar determinadas verificaciones. Estos encabezados **no sustituyen un proveedor de identidad**. El adaptador `DenyAllClinicalAuthorizationAdapter` restringe las operaciones veterinarias mientras se implementa la autorización correspondiente.

La URL local de Swagger responde al formato `https://localhost:<PUERTO>/swagger`, sin que ello constituya una publicación en cloud.

**Tabla de documentación por endpoint del sprint**

| Método y ruta | Path/Header/Body/Query Params | Request JSON | Response JSON / códigos | URL Swagger | Captura / commit |
|---|---|---|---|---|---|
| [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] |

**[PENDIENTE: DOCUMENTACIÓN OPENAPI VINCULADA AL SPRINT, EJEMPLOS REALES, SCREENSHOTS Y COMMITS DE DOCUMENTACIÓN.]**

#### 7.2.1.7. Software Deployment Evidence for Sprint Review

El despliegue de VetPax deberá documentarse mediante las acciones realmente desarrolladas durante la iteración, como preparación de entornos, configuración de la base de datos, publicación de servicios, integración de dependencias y verificación posterior.

El avance técnico conocido contempla la ejecución **local** del backend, el uso de MySQL y las migraciones de EF Core. No se dispone de evidencia de despliegue público o cloud de la API, la aplicación web, la aplicación móvil o la Landing Page.

| Producto / servicio | Actividad efectivamente documentada | Evidencia faltante |
|---|---|---|
| Backend API | Ejecución local con ASP.NET Core. | [PENDIENTE: CAPTURAS, URL/PROVEEDOR CLOUD Y RELACIÓN AL SPRINT] |
| MySQL | Bases locales y migraciones. | [PENDIENTE: CAPTURA/LOG DE MIGRACIÓN Y CONFIGURACIÓN CLOUD] |
| Web Application | Tecnología Angular 21 confirmada. | [PENDIENTE: EVIDENCIA DE BUILD Y PUBLICACIÓN] |
| Mobile Application | Tecnología Flutter/Dart confirmada. | [PENDIENTE: BUILD Y DISTRIBUCIÓN] |
| Landing Page | Diseño documentado en capítulos anteriores. | [PENDIENTE: IMPLEMENTACIÓN Y URL] |

**[PENDIENTE: PASOS Y CAPTURAS DE DESPLIEGUE REALMENTE REALIZADOS EN EL SPRINT.]**

#### 7.2.1.8. Team Collaboration Insights during Sprint

La colaboración durante cada sprint se documentará con las analíticas de GitHub, commits y Pull Requests de los productos digitales. Se identificará la contribución real de cada miembro del equipo y las decisiones o dificultades relevantes surgidas durante el desarrollo.

| Integrante | Repositorio | Actividad comprobada en Sprint 1 | Commit / Pull Request | Evidencia |
|---|---|---|---|---|
| Esteban Valentino Alvarez Falen | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] |
| Henry Kevin Diaz Gutierrez | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] |
| Rafael Alexander Dominguez Vargas | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] |
| Adrian Emanuel Valerio Garcia | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] | [PENDIENTE] |

**[PENDIENTE: CAPTURAS DE GITHUB INSIGHTS, COMMITS, RESPONSABILIDADES Y REFLEXIONES DEL SPRINT.]**

## 7.3. Validation Interviews

### 7.3.1. Diseño de Entrevistas

<!-- Reservado para la entrega final, según indicación del docente. -->

### 7.3.2. Registro de Entrevistas

**Segmento objetivo 1: Propietarios de mascotas geriátricas o con enfermedades crónicas**

| Campo | Información |
|---|---|
| Nombres y apellidos | |
| Edad | |
| Distrito | |
| Condición de la mascota | |
| Motivación | |
| Frustración | |
| Evidencia (captura) | |
| Link del video (Microsoft Stream) | |
| Duración / timing | |
| Resumen | |

**Segmento objetivo 2: Veterinarias y clínicas especializadas**

| Campo | Información |
|---|---|
| Nombres y apellidos | |
| Edad | |
| Distrito | |
| Rol en la clínica | |
| Motivación | |
| Frustración | |
| Evidencia (captura) | |
| Link del video (Microsoft Stream) | |
| Duración / timing | |
| Resumen | |

<!-- Duplicar cada tabla según las entrevistas que efectivamente se realicen. No registrar participantes, resultados ni videos ficticios. -->

### 7.3.3. Evaluaciones según heurísticas

<!-- Reservado para la entrega final. Utilizar el formato del Anexo D del enunciado oficial. -->

## 7.4. Video About-the-Product

**[PENDIENTE: VIDEO PUBLICADO, CAPTURA, DURACIÓN, URL DE MICROSOFT STREAM, URL DE YOUTUBE Y TESTIMONIO REAL CUANDO CORRESPONDA.]**

<!-- El enunciado solicita una primera versión del video en TB2. No atribuir su realización o publicación sin evidencia. -->
