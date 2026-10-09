# **Capítulo VI: Solution UX Design**

El presente capítulo desarrolla la propuesta de experiencia de usuario e interfaz de usuario de VetPax para los productos digitales que interactúan directamente con sus segmentos objetivo. Las decisiones de diseño consideran la Landing Page, la Web Application destinada principalmente a veterinarios y administradores de clínicas, y la Mobile Application orientada a propietarios de mascotas.

El diseño busca mantener una experiencia coherente entre los distintos productos de VetPax, sin perder las particularidades propias de cada plataforma y tipo de usuario. Para ello, se establecen lineamientos visuales comunes, principios de interacción y una arquitectura de información que facilite el acceso a las funcionalidades principales de la solución.

## **6.1. Style Guidelines**

Las Style Guidelines de VetPax establecen un lenguaje visual común para todos los productos digitales de la solución. Su objetivo es mantener consistencia entre la Landing Page, la Web Application y la Mobile Application mediante el uso uniforme de colores, tipografías, espaciado, componentes, iconografía y patrones de interacción.

La identidad visual de VetPax busca transmitir una combinación equilibrada entre el carácter profesional de una plataforma relacionada con el cuidado veterinario y una experiencia cercana para los propietarios de mascotas. Por este motivo, el diseño adopta una apariencia moderna, brillante, amigable y confiable, evitando tanto una estética excesivamente clínica como una representación demasiado infantil.

### **6.1.1. General Style Guidelines.**

#### **Branding**

VetPax es una plataforma digital orientada al seguimiento continuo de mascotas, especialmente aquellas geriátricas o que presentan enfermedades crónicas. Su identidad de marca se construye alrededor de cinco conceptos principales: confianza, cuidado, continuidad, claridad y profesionalismo.

La personalidad visual de la marca se define como moderna, cercana, serena y confiable. La intención es que los propietarios perciban una plataforma amigable que los acompaña durante el cuidado cotidiano de sus mascotas, mientras que los profesionales veterinarios identifiquen una herramienta organizada y apropiada para el seguimiento clínico.

El identificador visual de VetPax combina la representación de una mascota con la forma de un hogar, reforzando la idea de cuidado, protección y acompañamiento. Este concepto se complementa con el nombre VetPax y con la combinación de verde y azul como colores principales de la marca.

#### **Color System**

La paleta cromática utiliza colores brillantes y modernos. El verde constituye el color primario y representa cuidado, bienestar y salud, mientras que el azul funciona como color secundario y refuerza conceptos como confianza, tecnología y profesionalismo.

El color verde principal corresponde a `#14B8A6` y se utiliza principalmente en llamadas a la acción, elementos activos y componentes representativos de la marca. El azul `#3B82F6` se emplea para acciones secundarias, información complementaria y ciertos elementos de navegación.

Como color de acento se utiliza el ámbar `#F59E0B`, destinado principalmente a recordatorios, elementos destacados y aspectos asociados con la gamificación. El sistema se complementa con fondos claros y colores semánticos para representar estados del sistema.

Los colores principales definidos son:

- Primary Green: `#14B8A6`
- Secondary Blue: `#3B82F6`
- Accent: `#F59E0B`
- Background: `#F8FAFC`
- Surface: `#FFFFFF`
- Primary Text: `#0F172A`
- Secondary Text: `#64748B`
- Success: `#22C55E`
- Warning: `#F59E0B`
- Error: `#EF4444`

Los estados del sistema no dependerán exclusivamente del color. Siempre que sea necesario comunicar estados de éxito, advertencia o error, el color se acompañará de iconografía y etiquetas textuales que faciliten su interpretación.

<img src="./feature/Chapter-6/1_Styles.png" alt="VetPax Color System">

*Figura: Color System de VetPax.*

#### **Typography**

VetPax utiliza dos familias tipográficas principales. **Nunito Sans** se emplea en títulos y encabezados por su apariencia redondeada y cercana, mientras que **Inter** es utilizada para textos, formularios, botones, tablas y demás componentes de interfaz debido a su legibilidad en entornos digitales.

La jerarquía tipográfica establecida es la siguiente:

- H1: Nunito Sans, 32 px, Bold 700.
- H2: Nunito Sans, 28 px, Bold 700.
- H3: Nunito Sans, 24 px, SemiBold 600.
- H4: Nunito Sans, 20 px, SemiBold 600.
- Body Large: Inter, 18 px, Regular 400.
- Body: Inter, 16 px, Regular 400.
- Small Text: Inter, 14 px, Regular 400.
- Caption: Inter, 12 px, Regular 400.
- Button: Inter, 16 px, SemiBold 600.

En dispositivos móviles, determinados títulos pueden reducir ligeramente su tamaño cuando el espacio disponible lo requiera, manteniendo la jerarquía y legibilidad establecidas.

<img src="./feature/Chapter-6/2_Styles.png" alt="VetPax Typography Hierarchy">

*Figura: Typography Hierarchy de VetPax.*

#### **Spacing and Border Radius**

El sistema de espaciado se encuentra construido a partir de una unidad base de 8 px. Esta decisión permite mantener proporciones consistentes entre componentes, campos de formulario, tarjetas y secciones de contenido.

La escala definida es:

- XS: 4 px.
- S: 8 px.
- M: 16 px.
- L: 24 px.
- XL: 32 px.
- XXL: 48 px.

Los 4 px se reservan principalmente para pequeñas separaciones internas, mientras que 8 px y 16 px se utilizan entre elementos relacionados. Separaciones de 24 px, 32 px y 48 px permiten distinguir grupos de contenido y secciones completas.

VetPax utiliza formas redondeadas para reforzar su personalidad cercana y moderna. Los componentes pequeños utilizan un radio aproximado de 12 px; los botones e inputs emplean 16 px; las cards utilizan 20 px; los dialogs y modals utilizan 24 px; y los badges o chips utilizan bordes completamente redondeados.

<img src="./feature/Chapter-6/3_Styles.png" alt="VetPax Spacing System and Border Radius Scale">

*Figura: Spacing System and Border Radius Scale de VetPax.*

#### **Tone of Voice**

El tono de comunicación de VetPax se define como **profesional pero cercano**. La solución debe comunicar información relacionada con la salud y el seguimiento de las mascotas de manera clara y precisa, evitando generar preocupación innecesaria o utilizar un lenguaje excesivamente técnico con los propietarios.

En la dimensión divertido-serio, VetPax mantiene principalmente un comportamiento serio debido al contexto veterinario, permitiendo elementos positivos en los mensajes relacionados con logros y gamificación.

En la dimensión formal-casual se adopta una posición intermedia. La comunicación debe sentirse profesional sin resultar distante.

Respecto a la dimensión respetuoso-irreverente, VetPax mantiene siempre un lenguaje respetuoso tanto con propietarios como con profesionales veterinarios.

Finalmente, en la dimensión entusiasta-sereno predomina un tono sereno. El entusiasmo se utiliza de manera moderada cuando el usuario completa una tarea importante o alcanza un nuevo nivel de constancia.

Por ejemplo, para una notificación de medicación se prioriza un mensaje como *“Es momento de darle su medicamento a Luna”* sobre expresiones alarmistas como *“ALERTA: medicación pendiente”*.

### **6.1.2. Web, Mobile & Devices Style Guidelines.**

Los productos digitales de VetPax comparten el Design System definido previamente, pero adaptan su composición y sus patrones de interacción al contexto particular de cada plataforma.

Actualmente, VetPax contempla una Landing Page responsive, una Web Application y una Native Mobile Application. Debido a que el alcance actual de la solución no incorpora interfaces específicas para dispositivos IoT, las presentes guidelines se concentran en las experiencias Web y Mobile y en su funcionamiento sobre dispositivos de diferentes tamaños.

#### **Button System**

Los botones mantienen formas redondeadas y una jerarquía visual clara.

El **Primary Button** utiliza el verde `#14B8A6`, texto blanco y un radio de 16 px. Se utiliza para la acción principal de una pantalla, como guardar información, registrar una atención, confirmar una cita o agregar una mascota.

El **Secondary Button** utiliza el azul `#3B82F6` y se emplea para acciones complementarias que mantienen una relevancia importante dentro de la interfaz.

Los **Tertiary o Ghost Buttons** utilizan fondos transparentes y texto verde o azul, siendo empleados para acciones de menor prioridad como cancelar, regresar o acceder a información secundaria.

Cada variante contempla estados normal, hover, pressed, focus y disabled. En Mobile, los botones mantienen un área de interacción suficientemente amplia para facilitar su uso mediante controles táctiles.

<img src="./feature/Chapter-6/4_Styles.png" alt="VetPax Button System">

*Figura: Button System de VetPax.*

#### **Input Fields and Form Controls**

Los campos de entrada utilizan superficies blancas, bordes suaves y un radio aproximado de 16 px. Cada input debe presentar una etiqueta claramente visible y permitir identificar sus estados normal, focus, completed, disabled y error.

Los formularios mostrarán mensajes de validación próximos al campo que origina el problema, evitando que el usuario deba interpretar únicamente cambios de color.

La Web Application utilizará estos componentes especialmente en el registro de atenciones clínicas, edición de planes alimentarios y configuración de información de la clínica. En la aplicación móvil serán utilizados en procesos como registro de usuario, registro de mascotas y agendamiento de citas.

Los controles como switches, selectors, checkboxes y campos de fecha u hora conservarán el mismo lenguaje visual y se utilizarán únicamente cuando su comportamiento resulte adecuado para la información solicitada.

<img src="./feature/Chapter-6/5_Styles.png" alt="VetPax Input Fields and Form Controls">

*Figura: Input Fields and Form Controls de VetPax.*

#### **Chips, Badges and Semantic States**

Los chips y badges permiten representar categorías y estados de manera compacta. Utilizan formas completamente redondeadas y combinan texto, color e iconografía cuando resulta necesario.

En la Web Application pueden utilizarse para representar estados como *Pendiente*, *Atendida* o *Cancelada* dentro de la agenda. En Mobile pueden utilizarse para representar estados de una dosis como *Pendiente* o *Administrada*.

Los estados semánticos principales son Success, Warning y Error. Estos se apoyan en verde, ámbar y rojo respectivamente, manteniendo siempre una descripción textual para evitar depender exclusivamente de la percepción del color.

<img src="./feature/Chapter-6/6_Styles.png" alt="VetPax Chips Badges and Semantic States">

*Figura: Chips, Badges and Semantic States de VetPax.*

#### **Iconography**

VetPax utiliza iconografía de estilo **outline, redondeada y simple**. Los iconos mantienen un grosor visual consistente y evitan mezclar innecesariamente variantes outline con variantes filled.

Como referencia visual se adopta un estilo similar a Material Symbols Rounded. La biblioteca contempla iconos relacionados con mascotas, calendario, citas, historial clínico, medicación, alimentación, notificaciones, clínica, progreso, usuario y configuración.

Los iconos se acompañarán de etiquetas cuando su significado no resulte suficientemente evidente para el usuario.

<img src="./feature/Chapter-6/7_Styles.png" alt="VetPax Iconography Library">

*Figura: Iconography Library de VetPax.*

#### **Cards and Cross-Devices UI Patterns**

Las cards representan uno de los componentes principales de VetPax. Se utilizan superficies blancas, bordes suaves, sombras discretas y un radio aproximado de 20 px.

En la Web Application se utilizan principalmente para mostrar indicadores del Dashboard, datos resumidos de pacientes, próximas citas y bloques de información clínica. Cuando se necesita presentar una gran cantidad de registros, se priorizan tablas y listas estructuradas.

En Mobile, las cards adquieren mayor protagonismo debido al espacio disponible. Se utilizan para mostrar mascotas, próximas citas, medicamentos, planes alimentarios, recordatorios y progreso de constancia.

La información y las acciones se mantienen consistentes entre plataformas, aunque su composición se adapta al dispositivo. Una tabla de pacientes de escritorio, por ejemplo, puede transformarse en una lista de cards al reducirse el espacio disponible.

<img src="./feature/Chapter-6/8_Styles.png" alt="VetPax Card Examples and Cross Devices UI Patterns">

*Figura: Card Examples and Cross-Devices UI Patterns de VetPax.*

#### **Web Application Guidelines**

La Web Application se encuentra orientada principalmente a veterinarios y administradores de clínicas. La estructura utiliza una navegación lateral persistente en escritorio con las secciones **Inicio**, **Pacientes**, **Agenda** y **Clínica**.

Las funcionalidades específicas de un paciente no se presentan como opciones independientes de navegación global. En su lugar, al ingresar en un paciente se muestran secciones internas correspondientes a **Resumen**, **Historial clínico**, **Evolución** y **Plan alimentario**.

El diseño prioriza la visualización de información, el uso de tablas, filtros, calendarios y formularios, manteniendo suficiente espacio entre componentes para reducir la carga visual.

#### **Mobile Application Guidelines**

La Native Mobile Application está dirigida principalmente a propietarios de mascotas y utiliza una barra de navegación inferior con cinco secciones: **Inicio**, **Mascotas**, **Citas**, **Cuidados** y **Perfil**.

Las interacciones principales se diseñan considerando el uso táctil y el acceso rápido a acciones frecuentes. Las funciones relacionadas con medicación y alimentación se agrupan dentro de **Cuidados**, evitando aumentar innecesariamente el número de opciones principales de navegación.

Las interfaces utilizan principalmente cards y listas verticales en lugar de tablas. Los botones principales se ubican en zonas fácilmente alcanzables y se utilizan dialogs o bottom sheets para acciones secundarias cuando corresponda.

## **6.2. Information Architecture**

La Information Architecture de VetPax define la forma en que la información se estructura, etiqueta, busca y recorre dentro de la Landing Page, la Web Application y la Mobile Application.

Las decisiones se han establecido considerando las necesidades particulares de cada segmento. Los visitantes de la Landing Page requieren comprender rápidamente la propuesta de valor; los veterinarios necesitan localizar pacientes, citas e información clínica con rapidez; y los propietarios necesitan acceder fácilmente a sus mascotas, citas y actividades de cuidado cotidiano.

### **6.2.1. Organization Systems.**

VetPax combina diferentes sistemas de organización de acuerdo con el tipo de contenido y la tarea que realiza el usuario.

En la **Landing Page** predomina una organización jerárquica y secuencial. La información se presenta desde una visión general de la propuesta de valor hacia información más específica sobre beneficios, funcionalidades y segmentos objetivo. Las llamadas a la acción se ubican después de que el visitante dispone del contexto necesario para comprender el producto.

También se utiliza una organización basada en audiencia, diferenciando el contenido dirigido a propietarios de mascotas del contenido relacionado con veterinarios y clínicas.

En la **Web Application**, la organización principal es temática. El contenido se agrupa en Inicio, Pacientes, Agenda y Clínica. Dentro de Pacientes se utiliza nuevamente una organización jerárquica, ya que primero se accede al listado de pacientes, posteriormente al paciente seleccionado y finalmente a información específica como historial clínico, evolución o plan alimentario.

Los registros clínicos y determinadas actividades se presentan cronológicamente, ya que la fecha constituye un criterio relevante para comprender la evolución de una mascota.

La Agenda combina organización cronológica y temporal mediante vistas asociadas a fechas y horarios.

En la **Mobile Application**, la información también se organiza principalmente por tópicos: Inicio, Mascotas, Citas, Cuidados y Perfil. Las actividades de medicación y alimentación se agrupan dentro de Cuidados debido a que forman parte del seguimiento cotidiano de la mascota.

Determinados procesos utilizan una organización secuencial. El agendamiento de una cita, por ejemplo, guía al propietario a través de una serie de pasos como selección de mascota, selección de veterinaria, selección de fecha y hora y confirmación.

De esta manera, VetPax utiliza organización jerárquica para representar relaciones entre diferentes niveles de información, organización cronológica para historiales y citas, organización temática para las secciones principales y organización secuencial para procesos que deben completarse paso a paso.

### **6.2.2. Labeling Systems.**

El sistema de etiquetado de VetPax busca utilizar términos cortos, reconocibles y consistentes. Se evita utilizar terminología técnica cuando una expresión más sencilla puede comunicar el mismo significado a los propietarios de mascotas.

En la Landing Page se utilizan etiquetas asociadas con la propuesta de valor, los beneficios para cada segmento, testimonios y acciones de acceso al producto.

En la Web Application, las etiquetas principales corresponden a **Inicio**, **Pacientes**, **Agenda** y **Clínica**. Dentro de la información de un paciente se utilizan las etiquetas **Resumen**, **Historial clínico**, **Evolución** y **Plan alimentario**.

Las principales acciones se expresan mediante verbos que indican claramente el resultado esperado, por ejemplo: **Ver paciente**, **Registrar atención**, **Guardar atención**, **Editar plan alimentario**, **Marcar como atendida** y **Guardar cambios**.

En la Mobile Application, las etiquetas principales son **Inicio**, **Mascotas**, **Citas**, **Cuidados** y **Perfil**. Dentro de Cuidados se utilizan las categorías **Medicación** y **Alimentación**.

Las acciones utilizadas por propietarios también emplean expresiones directas, entre ellas **Agregar mascota**, **Agendar cita**, **Ver historial**, **Marcar como administrada**, **Reprogramar cita** y **Cancelar cita**.

Los estados se presentan mediante etiquetas breves y consistentes como **Pendiente**, **Confirmada**, **Atendida**, **Cancelada**, **Administrada**, **Próximo**, **Activo** e **Inactivo**, según corresponda al contexto.

Este sistema evita que una misma acción o concepto reciba nombres diferentes en distintas pantallas y favorece que el usuario pueda anticipar el resultado de cada interacción.

### **6.2.3. Searching Systems.**

Los sistemas de búsqueda de VetPax varían según el volumen de información disponible en cada producto.

La **Landing Page** no requiere un buscador interno debido a que presenta un volumen limitado de información y utiliza una estructura de navegación directa mediante secciones. El visitante puede desplazarse hacia la información requerida utilizando la navegación principal y las llamadas a la acción.

En la **Web Application**, la búsqueda adquiere mayor importancia debido al volumen potencial de pacientes y citas.

La sección Pacientes dispone de una barra de búsqueda que permite localizar registros principalmente a partir del nombre de la mascota o datos asociados al paciente. Esta búsqueda se complementa con filtros contextuales como especie, condición clínica y actividad reciente.

Los resultados se presentan dentro del mismo listado de pacientes, manteniendo visibles los criterios aplicados y permitiendo limpiar o modificar los filtros.

La Agenda utiliza criterios temporales y de estado para reducir la información mostrada. El veterinario puede consultar citas correspondientes a diferentes periodos y diferenciar entre citas próximas, pendientes o atendidas.

En la **Mobile Application** no se plantea un buscador global debido a que cada propietario administra un conjunto reducido de información asociado a su propia cuenta. En su lugar se priorizan mecanismos contextuales.

Cuando existen varias mascotas, el usuario puede seleccionar la mascota sobre la que desea consultar información. La sección Citas permite distinguir entre citas próximas y anteriores, mientras que Cuidados separa la información en Medicación y Alimentación.

Esta estrategia busca evitar introducir mecanismos de búsqueda innecesarios en pantallas donde la navegación mediante categorías y filtros simples resulta suficiente.


### **6.2.4. SEO Tags and Meta Tags.**

VetPax defines SEO Tags and Meta Tags for its Landing Page and Web Application in order to provide clear information about the purpose and content of each digital product to browsers and search engines. The metadata follows the information architecture and value proposition of the solution, while maintaining consistency with the terminology used across the platform.

As established for the digital products of the solution, English (`en_US`) is considered the default language. The metadata can also be localized to Latin American Spanish (`es_419`) as part of the internationalization strategy.

For the **Landing Page**, the following metadata is defined:

| Element | Value |
|---|---|
| Title | `VetPax | Continuous Veterinary Care for Your Pet` |
| Description | `VetPax helps owners care for geriatric pets and pets with chronic conditions through veterinary appointments, medication reminders, clinical history and nutrition plans.` |
| Keywords | `VetPax, veterinary care, pets, geriatric pets, chronic pet care, veterinary appointments, pet medication, clinical history` |
| Author | `PawVital Tech` |

The Landing Page metadata focuses on the general value proposition of VetPax because this product is intended to introduce the solution to visitors and direct each target segment to the appropriate digital product.

For the **Web Application**, metadata is defined according to its main pages and the tasks performed by veterinarians and clinic administrators.

| Page | Title | Description | Keywords | Author |
|---|---|---|---|---|
| Login | `VetPax | Veterinary Login` | `Secure access to the VetPax veterinary management platform.` | `VetPax, veterinary login, veterinary platform` | `PawVital Tech` |
| Dashboard | `VetPax | Veterinary Dashboard` | `Overview of appointments, patients and daily veterinary activities in VetPax.` | `VetPax, veterinary dashboard, patients, appointments` | `PawVital Tech` |
| Patients | `VetPax | Patient Management` | `Manage veterinary patients and access their clinical information and follow-up records.` | `VetPax, veterinary patients, clinical history, patient management` | `PawVital Tech` |
| Agenda | `VetPax | Veterinary Schedule` | `View and manage veterinary appointments and scheduled patient visits.` | `VetPax, veterinary appointments, schedule, veterinary agenda` | `PawVital Tech` |
| Clinic | `VetPax | Clinic Settings` | `Manage veterinary clinic information and opening hours in VetPax.` | `VetPax, veterinary clinic, clinic settings, opening hours` | `PawVital Tech` |

Since the Mobile Application may be distributed through an application store, VetPax also defines **App Store Optimization (ASO)** elements. These elements communicate the purpose of the application to pet owners and support its discoverability within mobile application stores.

| ASO Element | Value |
|---|---|
| App Title | `VetPax` |
| App Subtitle | `Your pet's care, always with you` |
| App Keywords | `pets, veterinary, appointments, medication, reminders, pet health, care` |
| App Description | `VetPax helps pet owners keep track of their pets' continuous care. The application provides access to clinical history, veterinary appointments, medication reminders, nutrition plans and care progress in one place.` |

These SEO, Meta Tag and ASO values maintain consistency with the terminology, target segments and value proposition of VetPax. Localized versions of the metadata will preserve the same meaning for the supported languages of the solution.

### **6.2.5. Navigation Systems.**

The navigation systems of VetPax are designed to provide a clear and predictable experience across the Landing Page, Web Application and Mobile Application. Each product uses navigation patterns adapted to its target audience and usage context while preserving consistent terminology, iconography and interaction principles.

The navigation structure prioritizes the most frequent tasks of each user segment. Pet owners require quick access to their pets, appointments and daily care activities, while veterinarians and clinic administrators require efficient access to patients, schedules and clinical information.

English (`en_US`) is used as the default language for interface labels. Equivalent labels can be provided in Latin American Spanish (`es_419`) through the internationalization capabilities of the solution.

#### **Mobile Application — Pet Owners**

The Mobile Application uses navigation patterns optimized for frequent, one-handed interaction and quick access to daily pet-care activities.

| Navigation Element | Description |
|---|---|
| **Bottom Navigation Bar** | Provides persistent access to the five main sections: **Home**, **Pets**, **Appointments**, **Care** and **Profile**. The selected destination is visually highlighted using the VetPax primary color. |
| **Hierarchical Navigation** | From **Pets**, the owner can select a pet and access its detailed information, including **Overview**, **Clinical History**, care information and nutrition-related information. |
| **Contextual Navigation** | Actions such as **View Appointment**, **View Clinical History**, **Mark as Administered** or **Schedule Appointment** appear next to the information associated with that action. |
| **Pet Selector** | When an owner has more than one registered pet, a contextual selector allows switching between pets without returning to the main pet list. |
| **Back Navigation** | Detail screens and multi-step processes provide a clear back action that returns the user to the previous level without losing the context of the task. |
| **Sequential Navigation** | Processes such as scheduling an appointment are divided into ordered steps: pet selection, clinic selection, date and time selection, reason for the appointment and confirmation. |
| **Visual Feedback** | Active navigation items, unread notifications, appointment states and medication states use consistent icons, labels and semantic colors to communicate the current system state. |

The Bottom Navigation Bar keeps the most important destinations permanently accessible. Secondary functionality is kept inside its corresponding section to avoid overloading the main navigation. For example, medication and nutrition are grouped under **Care** rather than being represented as independent navigation destinations.

#### **Web Application — Veterinarians and Clinic Administrators**

The Web Application uses a navigation system designed for information-intensive workflows and frequent movement between patient and appointment information.

| Navigation Element | Description |
|---|---|
| **Persistent Sidebar** | Provides permanent access to the main modules: **Home**, **Patients**, **Schedule** and **Clinic**. It remains visible on desktop interfaces and can collapse on smaller screens. |
| **Dashboard Navigation** | **Home** provides a summary of upcoming appointments, registered patients and relevant daily information, as well as shortcuts to frequently used modules. |
| **Hierarchical Navigation** | From **Patients**, the veterinarian first accesses the patient list and then selects a specific pet. The patient detail is divided into **Overview**, **Clinical History**, **Evolution** and **Nutrition Plan**. |
| **Contextual Navigation** | Relevant actions appear close to the information they affect. Examples include **View Patient** from an appointment, **Register Clinical Visit** from the clinical history and **Edit Nutrition Plan** from the active plan. |
| **Tabs** | Tabs are used inside the patient detail to switch between related information without returning to the global navigation menu. |
| **Breadcrumbs** | When the user navigates through several information levels, breadcrumbs indicate the current location. Example: `Home > Patients > Luna > Clinical History`. |
| **Role-Based Navigation** | Navigation options and available actions are adjusted according to the authenticated user's permissions. Administrative configuration in **Clinic**, for example, is available only to authorized users. |
| **Visual Feedback** | The active sidebar option, selected tabs, status chips and interactive elements provide immediate feedback regarding the current location and state of the interface. |

This structure separates global navigation from patient-specific navigation. As a result, modules such as Clinical History, Evolution or Nutrition Plan do not unnecessarily increase the number of options in the main sidebar.

#### **Landing Page — Visitors**

The Landing Page uses a simple navigation structure intended to help visitors understand the VetPax value proposition and reach the digital product corresponding to their segment.

| Navigation Element | Description |
|---|---|
| **Top Navigation Bar** | Provides direct access to the main informational sections of the Landing Page. It remains simple to avoid distracting visitors from the main value proposition. |
| **Anchor-Based Navigation** | Navigation links move the visitor directly to relevant sections within the same page, reducing unnecessary page changes. |
| **Audience-Based Navigation** | Content and Calls to Action distinguish between **Pet Owners** and **Veterinary Clinics**, allowing each visitor to identify the product designed for their needs. |
| **Call to Action Buttons** | Primary actions guide pet owners toward the Mobile Application and veterinary professionals toward the Web Application. |
| **Visual Hierarchy** | Headings, content sections, cards and Calls to Action guide the visitor progressively from the general value proposition toward specific product benefits and access options. |
| **Footer Navigation** | Provides secondary links such as contact information, Terms and Conditions, Privacy Policy and other institutional information. |

The Landing Page does not require deep navigation because its content is primarily informational. Its navigation therefore prioritizes vertical exploration, section anchors and clear Calls to Action.

#### **Cross-Platform Navigation Consistency**

VetPax maintains a consistent navigation language across its digital products. Similar concepts use the same terminology, iconography and interaction patterns whenever possible.

The Web Application emphasizes access to patient and clinic information, while the Mobile Application prioritizes daily care activities for pet owners. The Landing Page acts as the entry point to the ecosystem and directs each target segment toward the appropriate product.

This approach allows each interface to adapt its navigation to the characteristics of the device and user segment without losing the overall identity and predictability of the VetPax experience.


## **6.3. Landing Page UI Design**

La Landing Page de VetPax tiene como propósito comunicar de forma clara la propuesta de valor de la solución y orientar a los visitantes hacia la experiencia que les corresponde según su perfil. La página considera principalmente a propietarios de mascotas y profesionales o clínicas veterinarias.

El diseño mantiene coherencia con el Design System definido para VetPax, empleando la misma identidad visual, jerarquía tipográfica, sistema de espaciado, componentes, iconografía y criterios de interacción utilizados posteriormente en las aplicaciones Web y Mobile.

La estructura de la Landing Page sigue una secuencia progresiva: inicialmente presenta el propósito de VetPax, posteriormente explica su propuesta de valor y funcionamiento, muestra las soluciones dirigidas a cada segmento objetivo y finalmente incluye elementos de confianza, preguntas frecuentes y llamados a la acción.

### **6.3.1. Landing Page Wireframe**

Los wireframes de la Landing Page representan la primera aproximación visual a la organización del contenido. Estos diseños de baja fidelidad permiten definir la distribución, jerarquía, secuencia de secciones y ubicación de los principales Call-to-Action antes de aplicar el Design System definitivo.

#### **Hero Section**

La sección Hero constituye el primer punto de contacto del visitante con VetPax. Su estructura prioriza el mensaje principal del producto, una breve explicación de su propósito y accesos diferenciados para propietarios de mascotas y profesionales veterinarios.

![Landing Page Wireframe - Hero Section](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/1_HeroSection.png)

#### **Value Proposition**

Esta sección presenta de manera resumida los principales beneficios que ofrece VetPax. La distribución mediante bloques permite comunicar rápidamente aspectos como continuidad del cuidado, acceso organizado a información y conexión entre propietarios y profesionales veterinarios.

![Landing Page Wireframe - Value Proposition](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/2_ValueProposition.png)

#### **About the Product**

La sección About the Product explica el propósito general de VetPax y su papel como plataforma de apoyo para la continuidad del cuidado veterinario. Su estructura permite representar la relación entre propietarios, la plataforma y las clínicas veterinarias.

![Landing Page Wireframe - About Product](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/3_AboutProduct.png)

#### **How It Works**

Esta sección organiza de manera secuencial las principales etapas de interacción con VetPax. Se busca que el visitante pueda comprender de forma rápida cómo se registra una mascota, cómo se gestionan sus cuidados y cómo se mantiene el seguimiento veterinario.

![Landing Page Wireframe - How It Works](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/4_HowItWorks.png)

#### **For Pet Owners**

Esta sección presenta la propuesta dirigida específicamente a propietarios de mascotas. Se destacan las principales actividades disponibles en la aplicación móvil, como consultar mascotas, revisar citas, visualizar cuidados y acceder al historial clínico.

![Landing Page Wireframe - For Pet Owners](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/5_ForPetOwners.png)

#### **For Clinics and Professionals**

Esta sección comunica la propuesta de VetPax dirigida a profesionales y clínicas veterinarias. Se presenta la aplicación Web como herramienta para gestionar pacientes, consultar fichas clínicas, organizar citas y registrar atenciones.

![Landing Page Wireframe - For Clinics and Professionals](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/6_ForClinicsAndProfessionals.png)

#### **Product Overview**

El Product Overview presenta de forma resumida las principales funcionalidades que conforman el ecosistema VetPax. La organización mediante un grid permite identificar rápidamente las capacidades más importantes de la solución.

![Landing Page Wireframe - Product Overview](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/7_ProductOverviewGrid.png)

#### **Continuity of Care**

Esta sección representa conceptualmente uno de los principales enfoques de VetPax: mantener la continuidad del cuidado de la mascota después de una consulta veterinaria. Se presenta el flujo desde la atención profesional hasta el seguimiento realizado en casa.

![Landing Page Wireframe - Continuity of Care](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/8_ContinuityOfCareBlock.png)

#### **Testimonials**

La sección Testimonials reserva espacios para presentar experiencias de los usuarios de VetPax. Su propósito es aportar confianza a futuros usuarios mostrando la percepción de propietarios y profesionales veterinarios.

![Landing Page Wireframe - Testimonials](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/9_TestimonialsSection.png)

#### **Video About the Product**

Esta sección está destinada a la presentación audiovisual de VetPax. El espacio permite incorporar posteriormente el Video About-the-Product, mediante el cual se explica el funcionamiento general de la solución.

![Landing Page Wireframe - Video Section](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/10_VideoSection.png)

#### **Frequently Asked Questions**

La sección FAQ organiza las principales dudas que podría tener un visitante respecto al uso y propósito de VetPax. Su estructura mediante elementos desplegables permite mantener la página limpia y evitar una carga excesiva de información.

![Landing Page Wireframe - FAQ](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/11_FAQSection.png)

#### **Final Call to Action**

La última sección vuelve a presentar las principales acciones disponibles para los dos segmentos objetivo, permitiendo continuar hacia la experiencia correspondiente de VetPax.

![Landing Page Wireframe - Final CTA](feature/Chapter-6/Figma_VetPax/Landing_Page/Wireframes/12_FinalCTA.png)

### **6.3.2. Landing Page Mock-up**

Los mock-ups representan la versión de alta fidelidad de la Landing Page. Para su elaboración se aplicó el Design System de VetPax, incorporando la identidad cromática, jerarquía tipográfica, espaciado, iconografía, componentes, botones, cards y demás elementos visuales establecidos previamente.

El diseño busca transmitir una imagen moderna, amigable, profesional y confiable, manteniendo al mismo tiempo coherencia visual con las aplicaciones Mobile y Web.

#### **Hero Section**

La versión final del Hero Section utiliza la identidad visual de VetPax para destacar el mensaje principal de la solución y los accesos correspondientes a propietarios y profesionales veterinarios.

![Landing Page Mock-up - Hero Section](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/1_HeroSection.png)

#### **Value Proposition**

Esta sección presenta los beneficios principales de VetPax mediante componentes visuales sencillos y consistentes con el Design System.

![Landing Page Mock-up - Value Proposition](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/2_ValueProposition.png)

#### **About the Product**

La sección explica visualmente el propósito de VetPax y la relación entre los distintos usuarios que forman parte del ecosistema de cuidado veterinario.

![Landing Page Mock-up - About Product](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/3_AboutProduct.png)

#### **How It Works**

Esta sección utiliza una representación secuencial para explicar de manera sencilla cómo un usuario puede comenzar a utilizar VetPax y mantener el seguimiento de sus mascotas.

![Landing Page Mock-up - How It Works](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/4_HowItWorks.png)

#### **For Pet Owners**

La sección para propietarios muestra la experiencia Mobile de VetPax y las principales funciones disponibles para el seguimiento cotidiano de una mascota.

![Landing Page Mock-up - For Pet Owners](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/5_ForPetOwners.png)

#### **For Clinics and Professionals**

La sección para clínicas y profesionales presenta la experiencia Web y sus principales herramientas para la gestión y seguimiento clínico de pacientes.

![Landing Page Mock-up - For Clinics and Professionals](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/6_ForClinicsAndProfessionals.png)

#### **Product Overview**

El Product Overview presenta las funcionalidades más representativas de VetPax mediante un grid de elementos visuales fácilmente identificables.

![Landing Page Mock-up - Product Overview](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/7_ProductOverviewGrid.png)

#### **Continuity of Care**

Esta sección refuerza visualmente la continuidad entre consulta veterinaria, indicaciones profesionales, cuidados realizados por el propietario y futuros controles.

![Landing Page Mock-up - Continuity of Care](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/8_ContinuityOfCareBlock.png)

#### **Testimonials**

Los testimonios se presentan mediante cards que permiten identificar de manera clara al tipo de usuario y su experiencia con la solución.

![Landing Page Mock-up - Testimonials](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/9_TestimonialsSection.png)

#### **Video About the Product**

La sección incorpora un espacio visual destacado para el Video About-the-Product, permitiendo complementar la explicación escrita con una demostración audiovisual de VetPax.

![Landing Page Mock-up - Video Section](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/10_VideoSection.png)

#### **Frequently Asked Questions**

La sección FAQ utiliza componentes desplegables para responder las principales consultas de los visitantes sin sobrecargar visualmente la Landing Page.

![Landing Page Mock-up - FAQ](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/11_FAQSection.png)

#### **Final Call to Action**

La sección final concentra nuevamente los principales llamados a la acción, permitiendo que propietarios y profesionales continúen hacia el producto correspondiente.

![Landing Page Mock-up - Final CTA](feature/Chapter-6/Figma_VetPax/Landing_Page/Muck_ups/12_FinalCTA.png)

---

## **6.4. Applications UX/UI Design**

VetPax cuenta con dos aplicaciones principales dirigidas a diferentes tipos de usuario. La Mobile Application está orientada a los propietarios de mascotas, mientras que la Web Application está destinada principalmente a médicos veterinarios y personal de clínicas veterinarias.

Ambos productos mantienen una identidad visual común mediante la aplicación del Design System de VetPax, pero adaptan la organización de la información y sus patrones de interacción a las necesidades específicas de cada segmento.

### **6.4.1. Applications Wireframes**

Los wireframes permitieron establecer la estructura, navegación y jerarquía de las vistas principales antes de aplicar los componentes visuales definitivos.

#### **Mobile Application Wireframes**

##### **Inicio**

La vista Inicio proporciona al propietario un resumen del estado actual de su mascota, los cuidados programados para el día y la próxima cita veterinaria.

![Mobile Application Wireframe - Inicio](feature/Chapter-6/Figma_VetPax/Mobil_Application/Wireframe/1_Inicio.png)

##### **Mascotas**

La sección Mascotas presenta los animales registrados por el propietario y ofrece acceso directo a la información individual de cada mascota.

![Mobile Application Wireframe - Mascotas](feature/Chapter-6/Figma_VetPax/Mobil_Application/Wireframe/2_Mascotas.png)

##### **Citas**

La sección Citas permite consultar las próximas citas y atenciones anteriores, además de proporcionar un punto de acceso al proceso de agendamiento.

![Mobile Application Wireframe - Citas](feature/Chapter-6/Figma_VetPax/Mobil_Application/Wireframe/3_Citas.png)

##### **Cuidados**

La sección Cuidados concentra las actividades asociadas a medicación y alimentación de la mascota, permitiendo al propietario llevar un seguimiento de las indicaciones realizadas.

![Mobile Application Wireframe - Cuidados](feature/Chapter-6/Figma_VetPax/Mobil_Application/Wireframe/4_Cuidados.png)

#### **Web Application Wireframes**

##### **Dashboard Veterinario**

El Dashboard constituye la pantalla inicial para el médico veterinario y proporciona un resumen de la jornada, próximas citas y pacientes que requieren seguimiento.

![Web Application Wireframe - Dashboard](feature/Chapter-6/Figma_VetPax/Web_Application/Wireframes/1_Dashboard.png)

##### **Pacientes**

La vista Pacientes presenta el directorio de pacientes de la clínica y facilita el acceso a sus respectivos perfiles e información clínica.

![Web Application Wireframe - Pacientes](feature/Chapter-6/Figma_VetPax/Web_Application/Wireframes/2_Pacientes.png)

##### **Agenda**

La Agenda permite visualizar la planificación semanal de citas y la distribución de las atenciones entre los médicos veterinarios.

![Web Application Wireframe - Agenda](feature/Chapter-6/Figma_VetPax/Web_Application/Wireframes/3_Agenda.png)

##### **Clínica**

La vista Clínica organiza la información general de la institución, horarios de atención y profesionales veterinarios asociados.

![Web Application Wireframe - Clínica](feature/Chapter-6/Figma_VetPax/Web_Application/Wireframes/4_Clínica.png)

### **6.4.2. Applications Wireflow Diagrams**

En esta sección se presentan los **Wireflow Diagrams** de las aplicaciones de VetPax. Estos diagramas combinan los wireframes previamente definidos con las relaciones de navegación entre las principales vistas, permitiendo representar de manera visual cómo los usuarios se desplazan dentro de cada aplicación para completar sus tareas principales.

Los wireflows fueron elaborados manteniendo la arquitectura de información y los sistemas de navegación definidos para cada tipo de usuario. De esta manera, sirven como base para la posterior elaboración de los mock-ups, User Flow Diagrams y prototipos interactivos.

#### **Mobile Application Wireflow**

El wireflow de la aplicación móvil representa la navegación principal realizada por el propietario de mascota dentro de VetPax.

El flujo parte desde la pantalla de **Inicio**, desde donde el propietario puede acceder a las principales secciones mediante la barra de navegación inferior. El recorrido mostrado incluye el acceso a **Mascotas**, **Citas** y **Cuidados**, manteniendo disponible la navegación entre las funcionalidades principales de la aplicación.

La vista de **Mascotas** permite consultar las mascotas registradas y acceder a su información clínica. La sección de **Citas** permite visualizar las próximas atenciones veterinarias y acceder a sus detalles. Finalmente, la sección de **Cuidados** concentra el seguimiento de la medicación y alimentación asociada a la mascota.

Este wireflow permite validar que las funciones principales se encuentren accesibles mediante una estructura de navegación consistente y predecible para el propietario.

![Mobile Application Wireflow](feature/Chapter-6/Figma_VetPax/Mobil_Application/User_flow/Proceso_Principal_Movil.png)

#### **Web Application Wireflow**

El wireflow de la aplicación web representa la navegación principal utilizada por los especialistas veterinarios dentro de VetPax.

El recorrido parte desde el **Dashboard o Inicio**, que proporciona un resumen de la actividad clínica y acceso a las funcionalidades principales. Desde el menú lateral, el especialista puede navegar hacia **Pacientes**, donde consulta el listado de pacientes vinculados a la clínica; hacia **Agenda**, donde visualiza y gestiona las citas veterinarias; y hacia **Clínica**, donde se presenta la información general y configuración básica de la organización.

La navegación lateral se mantiene constante durante todo el recorrido, permitiendo que el especialista acceda rápidamente a las diferentes áreas de trabajo sin perder el contexto de la aplicación.

Este wireflow permite verificar la coherencia de la navegación de la Web Application antes de aplicar los elementos visuales definitivos del Design System de VetPax.

![Web Application Wireflow](feature/Chapter-6/Figma_VetPax/Web_Application/User_flow/Proceso_Principal_Web.png)

En conjunto, ambos Wireflow Diagrams permiten comprobar la organización de las vistas y las rutas principales de navegación de VetPax, asegurando consistencia entre la arquitectura de información, los wireframes y los flujos de interacción posteriormente representados en los mock-ups y User Flow Diagrams.



### **6.4.3. Applications Mock-ups**

Los Applications Mock-ups representan las vistas de alta fidelidad de las aplicaciones de VetPax. Estas pantallas aplican el Design System definido para la solución y muestran con mayor precisión los elementos visuales, contenido, estados y componentes con los que interactúan los usuarios.

#### **Mobile Application Mock-ups**

##### **Inicio**

La pantalla Inicio proporciona al propietario un resumen de la jornada de cuidado de su mascota. Se presentan los cuidados pendientes, próxima cita, progreso y accesos rápidos hacia las funcionalidades más utilizadas.

![Mobile Application Mock-up - Inicio](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/1_Inicio.png)

##### **Historial Clínico**

Esta pantalla permite al propietario consultar de manera cronológica los principales registros clínicos de su mascota, incluyendo controles, evaluaciones e indicaciones realizadas por los profesionales veterinarios.

![Mobile Application Mock-up - Historial Clínico](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/2_Historial_Clínico.png)

##### **Citas**

La sección Citas presenta las próximas atenciones y las citas anteriores del propietario. Desde esta vista también se puede acceder al detalle de una cita o iniciar un nuevo agendamiento.

![Mobile Application Mock-up - Citas](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/3_Citas.png)

##### **Agendar Cita**

Esta pantalla contiene el formulario necesario para registrar una nueva cita veterinaria, seleccionando la mascota, clínica, profesional, fecha, hora y motivo de consulta.

![Mobile Application Mock-up - Agendar Cita](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/4_Agendar_Cita.png)

##### **Detalle de Cita**

La vista Detalle de Cita presenta la información completa de una atención programada y permite al propietario consultar su estado, profesional asignado, horario y motivo.

![Mobile Application Mock-up - Detalle de Cita](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/5_Detalle_de_Cita.png)

##### **Cuidados - Medicación**

Esta pantalla permite realizar el seguimiento de la medicación activa de la mascota. Se visualizan las dosis programadas, su estado y el historial de administración reciente.

![Mobile Application Mock-up - Cuidados Medicación](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/6_Cuidados.png)

##### **Cuidados - Plan Alimentario**

La segunda vista de Cuidados presenta las indicaciones relacionadas con el plan alimentario de la mascota, incluyendo horarios, cantidades e información asociada al seguimiento de la alimentación.

![Mobile Application Mock-up - Cuidados Plan Alimentario](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/7_Cuidados.png)

##### **Mis Mascotas**

La pantalla Mis Mascotas presenta las mascotas registradas por el propietario y resume información relevante como edad, raza, condición principal y estado actual de sus cuidados.

![Mobile Application Mock-up - Mis Mascotas](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/8_Mis_Mascotas.png)

##### **Perfil Clínico**

Esta vista centraliza la información principal de una mascota seleccionada y proporciona acceso a información clínica, tratamientos, próximas citas e historial.

![Mobile Application Mock-up - Perfil Clínico](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/9_Perfil_Clínico.png)

##### **Perfil**

La pantalla Perfil permite consultar y actualizar información básica de la cuenta del propietario, así como gestionar preferencias generales de la aplicación.

![Mobile Application Mock-up - Perfil](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/10_Perfil.png)

##### **Nueva Mascota**

La vista Nueva Mascota presenta el formulario necesario para registrar una nueva mascota y asociarla con la cuenta del propietario.

![Mobile Application Mock-up - Nueva Mascota](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/11_Nueva_Mascota.png)

##### **Notificaciones**

Esta pantalla concentra las notificaciones relacionadas con citas, medicación, alimentación y otros eventos vinculados con los cuidados previamente configurados.

![Mobile Application Mock-up - Notificaciones](feature/Chapter-6/Figma_VetPax/Mobil_Application/Muck_ups/12_Notificaciones.png)

#### **Web Application Mock-ups**

##### **Dashboard Veterinario**

El Dashboard proporciona al médico veterinario una visión resumida de la jornada, citas programadas, pacientes registrados y pacientes que requieren seguimiento prioritario.

![Web Application Mock-up - Dashboard Veterinario](feature/Chapter-6/Figma_VetPax/Web_Application/Muck_ups/1_Veterinario.png)

##### **Lista de Pacientes**

La vista Lista de Pacientes presenta el directorio clínico de la organización y permite localizar pacientes mediante búsqueda y filtros, además de acceder a su ficha.

![Web Application Mock-up - Lista de Pacientes](feature/Chapter-6/Figma_VetPax/Web_Application/Muck_ups/2_Lista_de_Pacientes.png)

##### **Detalle de Paciente**

La pantalla Detalle de Paciente centraliza la información principal del animal, incluyendo datos generales, condición clínica activa, tratamiento, propietario y próxima cita.

![Web Application Mock-up - Detalle de Paciente](feature/Chapter-6/Figma_VetPax/Web_Application/Muck_ups/3_Detalle_de_Paciente.png)

##### **Detalle de Paciente - Historial Clínico**

Esta vista presenta cronológicamente las atenciones y registros clínicos asociados al paciente seleccionado.

![Web Application Mock-up - Historial Clínico](feature/Chapter-6/Figma_VetPax/Web_Application/Muck_ups/4_Detalle_de_Paciente_Historial_Clínico.png)

##### **Detalle de Paciente - Evolución**

La pestaña Evolución permite al profesional revisar la variación de los principales indicadores clínicos utilizados para el seguimiento del paciente.

![Web Application Mock-up - Evolución](feature/Chapter-6/Figma_VetPax/Web_Application/Muck_ups/5_Detalle_de_Paciente_Evolución.png)

##### **Detalle de Paciente - Plan Alimentario**

Esta pantalla presenta las indicaciones alimentarias asociadas al paciente y permite mantener organizada la información relacionada con su plan de alimentación.

![Web Application Mock-up - Plan Alimentario](feature/Chapter-6/Figma_VetPax/Web_Application/Muck_ups/6_Detalle_de_Paciente_Plan_Alimentario.png)

##### **Agendar Cita**

La vista Agendar Cita proporciona al profesional un formulario para registrar una atención futura para el paciente seleccionado.

![Web Application Mock-up - Agendar Cita](feature/Chapter-6/Figma_VetPax/Web_Application/Muck_ups/7_Agendar_Cita.png)

##### **Registrar Atención**

La pantalla Registrar Atención permite documentar los principales datos derivados de una consulta veterinaria, incluyendo motivo, evaluación, indicaciones y tratamiento.

![Web Application Mock-up - Registrar Atención](feature/Chapter-6/Figma_VetPax/Web_Application/Muck_ups/8_Registrar_atencion.png)

##### **Agenda**

La Agenda presenta visualmente las citas programadas durante la semana y permite identificar los pacientes, profesionales y horarios correspondientes a cada atención.

![Web Application Mock-up - Agenda](feature/Chapter-6/Figma_VetPax/Web_Application/Muck_ups/9_Agenda.png)

##### **Clínica**

La sección Clínica presenta la información general de la organización veterinaria, horarios de atención y profesionales asociados a la institución.

![Web Application Mock-up - Clínica](feature/Chapter-6/Figma_VetPax/Web_Application/Muck_ups/10_Clinica.png)

### **6.4.4. Applications User Flow Diagrams**

En esta sección se presentan los **User Flow Diagrams** definidos para las aplicaciones que forman parte de VetPax. Estos diagramas representan las rutas de interacción que siguen los usuarios para alcanzar determinados objetivos dentro de la solución, tomando como base los User Stories previamente establecidos.

Los User Flows fueron elaborados considerando las vistas y mock-ups de cada aplicación, permitiendo representar la secuencia esperada de interacción y mantener consistencia con la arquitectura de información y navegación propuesta para VetPax.

#### **Web Application User Flows**

Los User Flows de la Web Application están orientados a las principales tareas realizadas por los especialistas veterinarios y la gestión de la clínica.

##### **US03 - Registrar Atención Clínica**

**User goal:** Permitir que el especialista veterinario registre la información correspondiente a una atención clínica realizada a un paciente.

El flujo representa la navegación necesaria para acceder al paciente correspondiente, iniciar el registro de una atención y completar la información clínica asociada.

![US03 - Registrar Atención Clínica](feature/Chapter-6/Figma_VetPax/Web_Application/User_flow/US03_Registrar_Atencion_Clinica.png)

##### **US06 - Gestionar Agenda de Citas**

**User goal:** Permitir que el especialista veterinario consulte y gestione las citas registradas dentro de la agenda de la clínica.

El flujo representa el acceso a la agenda y las principales interacciones relacionadas con la gestión de citas veterinarias.

![US06 - Gestionar Agenda de Citas](feature/Chapter-6/Figma_VetPax/Web_Application/User_flow/US06_Gestionar_Agenda_Citas.png)

##### **US10 - Visualizar Listado de Pacientes**

**User goal:** Permitir que el especialista veterinario consulte los pacientes asociados a la clínica y acceda a la información de un paciente específico.

El flujo muestra la navegación desde el listado general de pacientes hacia las vistas correspondientes al paciente seleccionado.

![US10 - Visualizar Listado de Pacientes](feature/Chapter-6/Figma_VetPax/Web_Application/User_flow/US10_Visualizar_Listado_Pacientes.png)

##### **US11 - Consultar Evolución de Paciente**

**User goal:** Permitir que el especialista veterinario consulte la evolución clínica registrada de un paciente.

El flujo representa el acceso al detalle del paciente y posteriormente a la sección de evolución, donde se visualiza la información relacionada con su seguimiento clínico.

![US11 - Consultar Evolución de Paciente](feature/Chapter-6/Figma_VetPax/Web_Application/User_flow/US11_Consultar_Evolucion_Paciente.png)

##### **US12 - Gestionar Perfil de Clínica**

**User goal:** Permitir la consulta y gestión de la información correspondiente al perfil de la clínica.

El flujo representa el acceso a la sección Clínica y las interacciones relacionadas con la administración de su información.

![US12 - Gestionar Perfil de Clínica](feature/Chapter-6/Figma_VetPax/Web_Application/User_flow/US12_Gestionar_Perfil_Clinica.png)

#### **Mobile Application User Flows**

Los User Flows de la Mobile Application están orientados a las principales tareas realizadas por los propietarios de mascotas dentro de VetPax.

##### **US01 - Registrar Mascota**

**User goal:** Permitir que el propietario registre una nueva mascota dentro de su cuenta de VetPax.

El flujo representa el acceso a la sección de mascotas, el inicio del registro y la incorporación de la nueva mascota a la aplicación.

![US01 - Registrar Mascota](feature/Chapter-6/Figma_VetPax/Mobil_Application/User_flow/US01_Registrar_Mascota.png)

##### **US02 - Consultar Historial Clínico**

**User goal:** Permitir que el propietario consulte el historial clínico de una de sus mascotas.

El flujo representa la selección de la mascota y el acceso a la información clínica disponible dentro de su perfil.

![US02 - Consultar Historial Clínico](feature/Chapter-6/Figma_VetPax/Mobil_Application/User_flow/US02_Consultar_Historial_Clinico.png)

##### **US04 - Agendar Cita Veterinaria**

**User goal:** Permitir que el propietario registre una nueva cita veterinaria para su mascota.

El flujo muestra la navegación desde la gestión de citas hasta el proceso de agendamiento correspondiente.

![US04 - Agendar Cita Veterinaria](feature/Chapter-6/Figma_VetPax/Mobil_Application/User_flow/US04_Agendar_Cita_Veterinaria.png)

##### **US05 - Cancelar o Reprogramar Cita**

**User goal:** Permitir que el propietario gestione una cita previamente registrada mediante su cancelación o reprogramación.

El flujo representa el acceso al detalle de una cita y las rutas disponibles para modificar su programación.

![US05 - Cancelar o Reprogramar Cita](feature/Chapter-6/Figma_VetPax/Mobil_Application/User_flow/US05_Cancelar_Reprogramar_Cita.png)

##### **US09 - Recibir Recordatorios de Alimentación**

**User goal:** Permitir que el propietario visualice los recordatorios asociados al plan de alimentación de su mascota.

El flujo representa cómo el usuario accede a la información correspondiente a los cuidados y recordatorios de alimentación.

![US09 - Recibir Recordatorios de Alimentación](feature/Chapter-6/Figma_VetPax/Mobil_Application/User_flow/US09_Recibir_Recordatorios_Alimentacion.png)

##### **US13 - Visualizar Nivel de Constancia**

**User goal:** Permitir que el propietario consulte su progreso y nivel de constancia en el cuidado de su mascota.

El flujo muestra el acceso desde el resumen de constancia hacia la vista de detalle, donde el propietario puede consultar su progreso acumulado.

![US13 - Visualizar Nivel de Constancia](feature/Chapter-6/Figma_VetPax/Mobil_Application/User_flow/US13_Visualizar_Nivel_Constancia.png)

##### **US14 - Recibir Reconocimiento por Ascenso de Nivel**

**User goal:** Informar al propietario cuando alcanza un nuevo nivel de constancia dentro de VetPax.

El flujo representa la notificación del reconocimiento obtenido como resultado del progreso del usuario en las actividades de cuidado de su mascota.

![US14 - Recibir Reconocimiento por Ascenso de Nivel](feature/Chapter-6/Figma_VetPax/Mobil_Application/User_flow/US14_Recibir_Reconocimiento_Ascenso_Nivel.png)

##### **US18 - Registrar Administración de Medicación**

**User goal:** Permitir que el propietario registre que una dosis de medicación indicada para su mascota ha sido administrada.

El flujo representa la interacción desde la sección de cuidados hasta el registro de la administración correspondiente.

![US18 - Registrar Administración de Medicación](feature/Chapter-6/Figma_VetPax/Mobil_Application/User_flow/US18_Registrar_Administracion_Medicacion.png)

En conjunto, estos User Flow Diagrams permiten representar los principales objetivos de interacción cubiertos por las aplicaciones de VetPax, manteniendo correspondencia con los User Stories, mock-ups y estructura de navegación definida para cada tipo de usuario.



## **6.5. Applications Prototyping**

En esta sección se presentan los prototipos interactivos desarrollados para las aplicaciones que forman parte de la solución VetPax. Los prototipos permiten simular la navegación entre las principales vistas, validar los flujos definidos previamente y comprobar la consistencia de la experiencia de usuario entre la aplicación móvil orientada a propietarios de mascotas y la aplicación web orientada a especialistas veterinarios.

Los prototipos fueron elaborados en Figma tomando como base los mock-ups, wireflows y user flows definidos anteriormente. La navegación propuesta busca mantener una interacción simple, predecible y coherente con el Design System de VetPax.

### **6.5.1. Mobile Application Prototype**

El prototipo de la aplicación móvil representa la experiencia del propietario de mascota dentro de VetPax. Incluye la navegación entre las principales funcionalidades de la aplicación, como la consulta de información de las mascotas, seguimiento clínico, citas veterinarias, cuidados, medicación, planes alimentarios, perfil y notificaciones.

Asimismo, el prototipo permite validar la estructura de navegación inferior definida para la aplicación móvil, compuesta por las secciones **Inicio**, **Mascotas**, **Citas**, **Cuidados** y **Perfil**.

El prototipo interactivo puede consultarse en el siguiente enlace:

[**VetPax Mobile Application Prototype – Figma**](https://www.figma.com/proto/w9edhFA6VCAvT7Rl3wKKe2/Mobil-Application?node-id=22-2411&t=CR6IkEqjYgPmg0Kf-1&scaling=min-zoom&content-scaling=fixed&page-id=20%3A2&starting-point-node-id=22%3A2475)

### **6.5.2. Web Application Prototype**

El prototipo de la aplicación web representa la experiencia de los especialistas veterinarios dentro de VetPax. Permite recorrer las principales vistas relacionadas con la gestión de pacientes, agenda veterinaria, información clínica, evolución del paciente, planes alimentarios, registro de atenciones y administración básica de la clínica.

La navegación del prototipo mantiene la estructura definida para la aplicación web mediante un menú lateral y las acciones principales asociadas al seguimiento clínico de los pacientes.

El prototipo interactivo puede consultarse en el siguiente enlace:

[**VetPax Web Application Prototype – Figma**](https://www.figma.com/proto/xUBTqYXN6DG591Wr9j4njh/Web-Application?node-id=31-4505&p=f&t=yaGOrsZicVQS44O0-1&scaling=min-zoom&content-scaling=fixed&page-id=29%3A2&starting-point-node-id=31%3A4505)

Los prototipos permiten comprobar la relación entre las decisiones de arquitectura de información, los sistemas de navegación y los flujos de interacción definidos para cada aplicación. Además, sirven como base para posteriores actividades de validación con usuarios y para la implementación de las interfaces de VetPax.

