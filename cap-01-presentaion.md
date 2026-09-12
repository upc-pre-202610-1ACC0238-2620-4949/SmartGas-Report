# Capítulo I: Presentación

## 1.1. Startup Profile
### 1.1.1. Descripción de la Startup
Somos **FireSecure**, una startup tecnológica orientada a la ingeniería de software y dedicada a la creación de plataformas web de monitoreo para la seguridad en infraestructuras residenciales y comerciales. Nuestro trabajo se centra en el desarrollo de arquitecturas orientadas a servicios (SOA) que centralizan y procesan datos de dispositivos IoT en la nube.

Nuestra misión es disminuir el riesgo de desastres por fugas de gas e incendios mediante un producto de software accesible, intuitivo y altamente responsivo. Aspiramos a convertirnos en el ecosistema digital líder en gestión de emergencias, brindando tranquilidad a nuestros usuarios al permitirles visualizar el estado de sus entornos y recibir notificaciones críticas desde cualquier dispositivo con acceso web.

### 1.1.2. Perfiles de integrantes del equipo
| Foto | Nombre | Descripción |
| --- | --- | --- |
|   | Gabriel Ferran Espinar Martínez (U202310436)| Estudiante de ingenieria de Software. Soy estudiante de la carrera de Ingeniería de Software, Me considero una persona trabajadora. Me interesa aprender constantemente en especial en áreas relacionadas a la tecnología y cuento con conocimientos en HTML, CSS, Javascript y SQL, lo cual puede servir en el desarrollo del proyecto.  |
|  | Vivar Cesar, David Ignacio (U202414424) |   |
|   | Rioja Nuñez, Franco Diego (U202221597 )  | 
|   | Huaman Olivos, Yeira Shari (U202210513) |   |
|   |Guevara Serrano, Diego Ismael (U202318951) |   |

## 1.2. Solution Profile
### 1.2.1 Antecedentes y problemática
En los últimos años, los incidentes relacionados con fugas de gas e incendios han representado una de las principales causas de pérdidas en los sectores doméstico y gastronómico. Tradicionalmente, los sistemas de prevención se han limitado a hardware analógico o alarmas locales que exigen la presencia física del usuario para ser efectivas.

La problemática central radica en la **ausencia de un monitoreo preventivo remoto y descentralizado**. Los propietarios de viviendas y administradores de cocinas no cuentan con una herramienta digital que procese en tiempo real el estado de sus instalaciones. Esta limitación impide una respuesta inmediata ante anomalías, incrementando exponencialmente el riesgo de desastres al no poder alertar a tiempo a las personas involucradas o a los servicios de emergencia.

Para solucionar este vacío, es imperativo desarrollar una plataforma web basada en la nube. Un sistema que no solo consolide la telemetría de los entornos protegidos, sino que provea un panel de control interactivo, historial estadístico de incidencias y un sistema automatizado de alertas de alta disponibilidad, operando de forma continua como el núcleo de soporte para la toma de decisiones críticas.

### 1.2.2 Lean UX Process.
    
### 1.2.2.1. Lean UX Problem Statements.
**Domain:** El dominio de aplicación de SmartGas se enfoca en el desarrollo de aplicaciones web distribuidas aplicadas a la seguridad y monitoreo en entornos culinarios, específicamente en viviendas y restaurantes. En este contexto, la integración de una plataforma web con servicios en la nube representa una alternativa innovadora para gestionar y visualizar riesgos asociados al gas y temperatura de forma remota.

**Customer Segments:** Los segmentos de clientes identificados son: 
* **Hogares:** Familias que buscan proteger sus viviendas mediante el monitoreo remoto de sus cocinas a través de una aplicación web accesible desde cualquier dispositivo. 
* **Restaurantes y establecimientos de comida:** Administradores y jefes de cocina responsables de garantizar la seguridad operativa y el cumplimiento de normativas en ambientes de alta demanda. 

**Pain Points:** Dificultad para visualizar en tiempo real el estado de seguridad de la cocina cuando el usuario se encuentra fuera del establecimiento o vivienda. 
* Dependencia de sistemas locales que no ofrecen una interfaz web para el registro histórico y análisis de datos de incidencias. 
* Complejidad en la gestión de múltiples sensores o ubicaciones sin una plataforma centralizada que unifique la información en un dashboard interactivo. 
* Riesgo de pérdidas materiales por la incapacidad de recibir notificaciones de alerta inmediatas en dispositivos móviles a través de la red. 

**Gap:** Existe una brecha tecnológica entre los dispositivos de detección aislados y la necesidad de contar con una plataforma web integral basada en una arquitectura orientada a servicios (SOA). Actualmente, el mercado peruano carece de soluciones SaaS masivas que reúnan accesibilidad económica, una aplicación web responsiva y una lógica de servidor capaz de automatizar respuestas preventivas y notificaciones en tiempo real. 

**Visión:** La visión de SmartGas es convertirse en el ecosistema web líder en seguridad inteligente para cocinas, capaz de centralizar la telemetría de sensores en una aplicación web robusta desarrollada en C#. El sistema permitirá monitorear riesgos y gestionar respuestas automáticas (notificaciones y actuadores) mediante una infraestructura en la nube. La estrategia se centra en la innovación de software, utilizando una arquitectura distribuida para demostrar que la prevención inteligente es gestionable desde cualquier navegador web en contextos cotidianos. 

**Initial Segment:** Nuestros dos segmentos objetivos definidos son estratégicos porque presentan una alta exposición a riesgos de gas y temperatura, y actualmente carecen de una plataforma web de gestión centralizada. Validar el sistema en estos entornos permite demostrar la eficacia de nuestra aplicación web y su valor preventivo. Por ello nuestra pregunta clave es: ¿Cómo puede una aplicación web distribuida como SmartGas , que integra una API RESTful en C# con servicios de notificación externos, proporcionar una gestión de seguridad eficiente y accesible para disminuir los riesgos de accidentes en cocinas domésticas y comerciales?

### 1.2.2.2. Lean UX Assumptions.
**Assumptions Worksheet**
* **¿Quiénes creemos que serán nuestros usuarios?** 
    * Propietarios de viviendas que utilizan aplicaciones web para la domótica. 
    * Gerentes y administradores de locales de comida rápida y restaurantes. 
    * Personal técnico encargado del mantenimiento de seguridad en edificios. 
* **¿Qué creemos que necesitan estos usuarios?** 
    * Monitorear el estado de su seguridad desde una aplicación web responsiva. 
    * Reducir la incertidumbre mediante la visualización de datos en tiempo real. 
    * Contar con un sistema basado en la nube que actúe rápido y envíe alertas digitales sin intervención manual constante. 
    * Acceder a un historial de reportes y eventos de seguridad a través de un panel de control interactivo. 
* **¿Qué espera lograr el proyecto?** 
    * Desarrollar una solución web distribuida bajo el modelo SaaS. 
    * Ofrecer un producto innovador basado en tecnologías open-source y lenguaje C#. 
    * Demostrar que la integración de aplicaciones web con IoT puede prevenir pérdidas humanas y materiales. 
    * Diferenciarse en el mercado mediante un dashboard avanzado de gestión de riesgos. 
* **¿Qué esperamos que pase si la propuesta es válida?** 
    * Alta adopción de la plataforma web en el sector gastronómico local. 
    * Validación de la arquitectura SOA como una base sólida para la escalabilidad del negocio. 
    * Satisfacción del usuario al interactuar con una interfaz web intuitiva y de alta disponibilidad. 

**Business Assumptions**
* Posicionar a SmartGas como la plataforma web líder en monitoreo de seguridad preventiva. 
* Generar confianza en el mercado SaaS mediante un sistema de suscripción confiable y seguro. 
* El mantenimiento de la aplicación web y la lógica de servidor no representará un sobrecosto excesivo para el cliente. 
* La lógica de lado servidor en C# actuará con precisión, procesando los datos de los sensores sin generar falsos positivos en la interfaz. 
* Los usuarios verán en la aplicación web SmartGas una herramienta indispensable para la continuidad de su negocio. 

**User Outcome**
* **Cocinas Domésticas (Familias):** 
    * Los usuarios sienten tranquilidad al saber que pueden verificar su hogar desde cualquier navegador web. 
    * No necesitan ser expertos técnicos; la aplicación web ofrece visualizaciones claras y amigables. 
* **Restaurantes (Administradores):** 
    * Un dashboard principal que centraliza múltiples locales, permitiendo una gestión operativa eficiente. 
    * Evitan daños en infraestructura costosa gracias a la rapidez de las notificaciones web y acciones automáticas del backend. 

**Features**
* **Cocinas Domésticas (Familias):** 
    * Interfaz responsiva con estados de seguridad en tiempo real. 
    * Envío de alertas críticas a través de integración con servicios de mensajería (SMS/Push) desde el servidor. 
* **Restaurantes (Administradores):** 
    * Panel de control administrativo con gráficas estadísticas de niveles de gas y temperatura. 
    * Gestión de usuarios y roles para el personal de seguridad y administración. 
    * API RESTful robusta que asegura la comunicación continua entre los dispositivos y la aplicación web.

### 1.2.2.3. Lean UX Hypothesis Statements.
**Business Hypothesis**
Si logramos desarrollar una plataforma web que no solo centralice los datos, sino que además permita gestionar respuestas automáticas y notificaciones remotas a través de una arquitectura SOA en C#, entonces los usuarios percibirán un alto valor preventivo y comercial, lo que se traducirá en una rápida adopción del modelo de suscripción SaaS y una ventaja competitiva frente a sistemas de alarma locales que no ofrecen conectividad web.

**User Hypothesis**
* **Cocinas Domésticas (Familias):** Creemos que las familias necesitan una aplicación web de seguridad intuitiva que les permita monitorear su hogar remotamente, ya que su prioridad es la protección de sus seres queridos sin lidiar con configuraciones técnicas complejas. 
* **Restaurantes (Administradores):** Creemos que los administradores de restaurantes necesitan una plataforma SaaS que automatice la prevención y centralice la información de múltiples zonas, ya que su prioridad es asegurar la continuidad del negocio y proteger sus activos mediante decisiones basadas en datos en tiempo real.
### 1.2.2.4. Lean UX Canvas.



## 1.3. Segmentos objetivo
**Segmento Doméstico: Familias y Propietarios de Viviendas**
Este segmento está compuesto por familias o individuos que residen en hogares urbanos y buscan proteger sus viviendas de accidentes relacionados con el uso de gas y riesgos eléctricos.

* **Perfil y Comportamiento:** Usuarios familiarizados con el uso de aplicaciones móviles cotidianas, pero que no necesariamente poseen conocimientos técnicos avanzados en redes o infraestructura.
* **Necesidad Tecnológica:** Requieren una app móvil intuitiva y responsiva que les permita visualizar el estado de seguridad de sus cocinas en tiempo real. Su prioridad es recibir notificaciones push de alerta tempranas directamente en sus dispositivos, permitiéndoles tomar acción inmediata sin necesidad de supervisión presencial constante.

**Segmento Comercial: Administradores y Chefs de Restaurantes**
Este segmento abarca a dueños de negocios, administradores y jefes de cocina responsables de garantizar la seguridad operativa en establecimientos de comida, restaurantes y ambientes de alta demanda.

* **Perfil y Comportamiento:** Profesionales enfocados en la continuidad del negocio, la protección de su personal y el cumplimiento de estándares de seguridad. Manejan operaciones críticas y necesitan herramientas de gestión unificadas.
* **Necesidad Tecnológica:** Requieren un panel de control móvil avanzado soportado por una arquitectura orientada a servicios (SOA). Necesitan visualizar datos históricos de sensores, gestionar múltiples zonas de la cocina y confiar en una lógica de lado servidor robusta que no solo notifique las emergencias, sino que centralice la automatización de acciones preventivas para evitar la paralización de sus operaciones comerciales.
