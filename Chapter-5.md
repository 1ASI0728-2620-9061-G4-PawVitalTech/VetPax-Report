## **Capítulo V: Tactical-Level Software Design**
### 5.1 Pet & Clinical Care
### 5.2 Clinic Management
### 5.3. Appointment Management

Appointment Management administra la programación, reprogramación, cancelación y registro de atención de citas veterinarias. Su propósito es mantener la agenda sin conflictos de horario y contribuir a la continuidad del seguimiento de las mascotas. Se clasifica como un subdominio de soporte y cumple el rol de Execution Context.

El contexto utiliza la referencia de la mascota proporcionada por Pet & Clinical Care, los horarios de atención de Clinic Management y la identidad y permisos gestionados por IAM. Publica eventos sobre el ciclo de vida de las citas y se integra con el servicio externo de calendario. El registro de diagnósticos y atenciones clínicas pertenece a Pet & Clinical Care; el cálculo de adherencia pertenece a Adherence & Gamification.

| Referencia | Responsabilidad que sustenta |
| --- | --- |
| US04 — Agendar cita veterinaria | Registrar una cita con mascota, fecha, hora y motivo cuando existe disponibilidad. |
| US05 — Cancelar o reprogramar cita | Modificar una cita pendiente, liberar el horario al cancelarla y evitar duplicados al reprogramarla. |
| US06 — Gestionar agenda de citas | Consultar la agenda por periodo y permitir que el veterinario registre una cita como atendida. |
| TS03 — API para gestionar citas veterinarias | Exponer la creación y actualización de citas y comunicar los conflictos de horario. |
| TS04 — Integración de citas con servicio de calendario | Sincronizar las citas confirmadas y conservar la cita interna si el proveedor externo falla. |
| Secciones 4.2.1, 4.2.4 y 4.2.5 | Establecer el agregado Appointment, los mensajes del contexto y sus relaciones con otros contextos. |

#### 5.3.1. Domain Layer

La Domain Layer concentra las reglas que controlan el ciclo de vida de una cita. Mantiene el modelo de negocio separado de las solicitudes HTTP, la base de datos y el proveedor de calendario, de acuerdo con la arquitectura hexagonal definida en ADD01 y ADD02.

**Aggregate Root**

El agregado **Appointment**, identificado en el EventStorming, representa una cita veterinaria. Centraliza los cambios relacionados con su programación, reprogramación, cancelación y atención. La información requerida por US04 comprende la mascota, la fecha, la hora y el motivo; la cita queda vinculada con la agenda correspondiente.

Las operaciones sobre una cita dependen de su estado: las citas pendientes admiten cancelación o reprogramación, mientras que las atendidas o canceladas no pueden modificarse.

**Reglas de negocio**

| Operación | Regla de negocio | Resultado esperado |
| --- | --- | --- |
| Agendar | El horario debe estar disponible y los datos obligatorios deben estar completos. | Se registra la cita y se vincula con la agenda correspondiente. |
| Rechazar una reserva | Un horario ocupado no puede reservarse nuevamente. | La solicitud se rechaza y se informa el conflicto. |
| Reprogramar | La cita debe estar pendiente y el nuevo horario debe estar disponible. | Se actualizan la fecha y la hora sin duplicar la cita. |
| Cancelar | La cita debe encontrarse pendiente. | Se cambia a cancelada y se libera el horario reservado. |
| Restringir modificaciones | Una cita atendida o cancelada no puede modificarse. | Se rechaza la operación. |
| Marcar como atendida | Según US06, el veterinario registra la atención de una cita pendiente. | Se actualiza el estado de la cita. |

La disponibilidad requiere considerar tanto las reservas existentes como los horarios que proporciona Clinic Management.

**Domain Events**

| Evento | Hecho representado |
| --- | --- |
| `CitaVeterinariaProgramada` | Se ha registrado una cita válida. |
| `CitaVeterinariaReprogramada` | Se ha modificado el horario de una cita pendiente. |
| `CitaVeterinariaCancelada` | Se ha cancelado una cita y liberado su horario. |
| `CitaVeterinariaAtendida` | El veterinario ha registrado la cita como atendida. |

Adherence & Gamification consume `CitaVeterinariaAtendida` como evidencia para su cálculo. Appointment Management comunica el hecho ocurrido sin incorporar las reglas de niveles o porcentajes de constancia.

**Repository Interfaces y modelo de consulta**

La persistencia del agregado requiere un contrato para registrar, recuperar y actualizar citas, así como consultar las reservas necesarias para verificar disponibilidad. Su implementación corresponde a Infrastructure Layer.

El Read Model **Agenda veterinaria**, identificado en el EventStorming, permite consultar las citas ordenadas por fecha y hora, con la información necesaria del paciente. Esta consulta no modifica el estado del agregado.

| Elemento | Tipo | Responsabilidad |
| --- | --- | --- |
| Appointment | Aggregate Root | Representar la cita y controlar los cambios de su ciclo de vida. |
| Eventos del ciclo de la cita | Domain Events | Comunicar programación, reprogramación, cancelación y atención. |
| Contrato de persistencia de citas | Abstracción de repositorio | Separar las operaciones de almacenamiento de la tecnología utilizada. |
| Agenda veterinaria | Read Model | Presentar las citas para la consulta del veterinario. |


- 5.X. Bounded Context: <Bounded Context Name>
    - 5.X.1. Domain Layer
    - 5.X.2. Interface Layer
    - 5.X.3. Application Layer
    - 5.X.4. Infrastructure Layer
    - 5.X.6. Bounded Context Software Architecture Component Level Diagrams
    - 5.X.7. Bounded Context Software Architecture Code Level Diagrams
        - 5.X.7.1. Bounded Context Domain Layer Class Diagrams
        - 5.X.7.2. Bounded Context Database Design Diagram
