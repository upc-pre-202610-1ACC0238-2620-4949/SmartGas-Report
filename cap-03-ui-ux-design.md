# Capítulo III: Solution UI/UX Design

## 3.1. Product design

El diseño de producto de SmartGas parte de una premisa obtenida en las entrevistas: el usuario abre la app en dos situaciones muy distintas, una de calma (revisar que todo esté bien antes de salir o durante el servicio) y una de urgencia (una alerta de fuga). Por ello, cada decisión de diseño busca que el estado de seguridad se entienda en menos de cinco segundos y que, en una emergencia, la acción correcta sea también la más visible.

Las decisiones clave que guían el diseño son:

- **Estado primero.** El dashboard prioriza el estado general (Safe, Warning, Critical) sobre cualquier otro dato, con color, ícono y texto, de modo que el estado no dependa solo del color.
- **Acción guiada en emergencias.** Las alertas críticas abren una vista con la guía de respuesta, la confirmación y la llamada directa al contacto de emergencia o al 116.
- **Consistencia entre productos.** El landing page, la app Android y la app Flutter comparten la paleta, la tipografía, los íconos y el tono de comunicación, y se basan en Material Design 3.
- **Accesibilidad e internacionalización desde el inicio.** Áreas táctiles de 48 dp como mínimo, contraste según WCAG 2.1 AA, descripciones para lectores de pantalla y textos externalizados en inglés (`en_US`, idioma por defecto) y español latinoamericano (`es_419`).
- **Tecnologías.** Jetpack Compose con Material 3 en Android; Flutter con Material 3 en los Sprints 3 y 4; HTML5, CSS3 y JavaScript en el landing page.

### 3.1.1. Style Guidelines

Las guías de estilo constituyen el repositorio común de decisiones visuales del equipo: logotipo, tipografía, colores, espaciado, íconos y tono de comunicación. Se organizan en guías generales, guías para la web (landing page) y guías para las aplicaciones móviles. Los recursos se mantienen en el archivo de Figma del equipo y en el tema de cada aplicación (`SmartGasTheme` en Compose).

#### 3.1.1.1. General Style Guidelines

**Branding**

El nombre **SmartGas** combina *Smart* (inteligencia aplicada al IoT y a la automatización) y *Gas* (el recurso crítico que se busca proteger). El logotipo representa una llama formada por nodos y líneas dentro de un escudo: los nodos simbolizan la telemetría de los sensores y el escudo, la protección. El degradado del naranja al azul expresa la transformación de un peligro latente en un entorno controlado.

<div align="center">
  <img alt="Logotipo de SmartGas" src="assets/22-Logo_SmartGas.png" width="220" />
</div>

**Tipografía**

- **Koulen** se reserva para el logotipo y los titulares de marca del landing page. Sus formas anchas y fuertes transmiten solidez, pero no se usa en textos largos ni en la app, donde afectaría la legibilidad.
- **Roboto** es la tipografía de la interfaz de la app y del cuerpo de texto. Es la fuente por defecto de Material Design, está optimizada para pantallas pequeñas y admite todos los caracteres del español.

<div align="center">
  <img alt="Tipografía Koulen" src="assets/23-Tipografia_Koulen.png" width="350" />
</div>

**Colores**

| Token | Color | Uso |
|:--|:--|:--|
| Primary | `#066CBB` | Color principal de la marca: botones, navegación activa y enlaces. Transmite confianza y estabilidad. Contraste de 5,4:1 sobre blanco. |
| Secondary | `#E6501F` | Acento de marca asociado al fuego bajo control. Se usa en íconos y elementos grandes, no en texto pequeño (contraste de 3,8:1). |
| Tertiary | `#C38967` | Tono de transición del degradado de la marca; se usa en ilustraciones y fondos decorativos. |
| Safe | `#1E8E3E` | Estado seguro. |
| Warning | `#E37400` | Estado de advertencia y severidad alta; siempre acompañado de ícono y texto. |
| Critical | `#D93025` | Estado crítico y acciones de emergencia (contraste de 4,8:1). |
| Surface / On surface | `#F6F9FC` / `#1B1F24` | Fondos y texto principal. |

**Spacing**

Todo el sistema utiliza una retícula de 4 px (4 dp en móvil) con los valores 4, 8, 12, 16, 24 y 32. Los márgenes laterales son de 16 dp en la app y de 24 px en el landing page en móvil. El espacio en blanco agrupa la información relacionada y separa los bloques de estado de los de acción.

**Tono de comunicación y lenguaje**

Según las cuatro dimensiones del tono de voz de Nielsen Norman Group, SmartGas se comunica de forma **seria** (no humorística, porque trata la seguridad de las personas), **cercana** (casual sin perder el profesionalismo, pensando en familias sin conocimientos técnicos), **respetuosa** y **directa** (sin entusiasmo exagerado). En situaciones de emergencia los mensajes son cortos, en imperativo y con una sola instrucción por línea: «Close the cylinder valve if it is safe».

#### 3.1.1.2. Web Style Guidelines

- El landing page se diseña con enfoque *mobile-first* y puntos de quiebre en 600 px y 1024 px.
- Se mantiene el patrón de lectura en Z para la sección principal: logotipo, menú, mensaje de valor y llamado a la acción.
- Los botones primarios usan el color Primary con texto blanco y una altura mínima de 44 px.
- Todo el contenido existe en inglés y en español mediante atributos `data-lang`, con selector de idioma en el encabezado.
- Las imágenes incluyen texto alternativo y los controles de navegación, atributos ARIA (`aria-label`, `aria-expanded` en el menú móvil).

<div align="center">
  <img alt="Diseño responsive del landing page" src="assets/24-Web_Responsive_Breakpoints.png" width="450" />
</div>

#### 3.1.1.3. Mobile Style Guidelines

La app Android sigue las guías de Material Design 3 y las *Core App Quality guidelines* de Android; la app Flutter usará los mismos tokens mediante `ThemeData` con `useMaterial3: true`.

<div align="center">
  <img alt="SmartGas Mobile Style Guide" src="assets/25-Mobile_Style_Guide.png" />
</div>

- **Componentes:** Top App Bar, Navigation Bar inferior con cinco destinos, Cards para zonas y alertas, Filter Chips, Floating Action Button para agregar, Sliders para umbrales y Switches para preferencias.
- **Áreas táctiles:** mínimo 48 × 48 dp; las acciones de emergencia usan botones de ancho completo.
- **Estados:** cada estado combina color, ícono y texto (por ejemplo, ícono `verified_user` y la etiqueta «SAFE»).
- **Accesibilidad:** `contentDescription` en todos los íconos con significado, soporte de TalkBack, tamaños de fuente en sp para respetar la configuración del sistema y contraste mínimo de 4,5:1 en textos.
- **Internacionalización:** todos los textos se definen en `res/values/strings.xml` (inglés) y `res/values-b+es+419/strings.xml` (español latinoamericano); fechas y números con el formato de la configuración regional.
- **Tema oscuro:** los tokens tienen su versión oscura y la app respeta la preferencia del sistema.

### 3.1.2. Information Architecture

La arquitectura de información define cómo se organiza, rotula, busca y recorre el contenido del landing page y de las aplicaciones móviles para que visitantes y usuarios encuentren lo que necesitan sin esfuerzo, sobre todo en una emergencia.

#### 3.1.2.1. Organization Systems

| Producto | Grupo de información | Organización visual | Esquema de categorización |
|:--|:--|:--|:--|
| Landing Page | Propuesta de valor, beneficios, características, app, planes, equipo y contacto | Secuencial (de la concientización del riesgo a la descarga y el contacto) | Por tópicos |
| Landing Page | Planes | Matricial (tres tarjetas comparables) | Por audiencia (hogar, negocio pequeño, negocio con varias zonas) |
| App móvil | Home (dashboard) | Jerárquica: estado general → indicadores → zonas → clima | Por relevancia del riesgo |
| App móvil | Zones | Jerárquica (zona → sensores → lecturas) | Por ubicación (espacial) y por estado |
| App móvil | Alerts | Jerárquica | Cronológico, ordenado primero por severidad |
| App móvil | Alert detail | Secuencial (step-by-step) | Pasos de respuesta numerados |
| App móvil | History | Lista con filtros | Cronológico, con filtros por zona y severidad |
| App móvil | Add sensor | Secuencial (escanear o ingresar → elegir zona → guardar) | — |
| App móvil | Settings | Jerárquica por grupos | Por tópicos (seguridad, notificaciones, cuenta) |

#### 3.1.2.2. Labeling Systems

Las etiquetas son cortas, usan palabras de acción para los comandos y mantienen el mismo término para el mismo concepto en todos los productos (por ejemplo, *Alert* siempre es el aviso al usuario e *Incident* el riesgo registrado). El idioma por defecto es el inglés; la tabla incluye su equivalente en español latinoamericano.

| Producto | Etiqueta (en_US) | Equivalente (es_419) | Asociación |
|:--|:--|:--|:--|
| Landing | Home · About us · Benefits · Features · Get the app · Plans · Team · Contact | Inicio · Nosotros · Beneficios · Características · Descarga la app · Planes · Equipo · Contacto | Secciones del menú |
| Landing | Download for Android · Select · Send message | Descargar para Android · Elegir · Enviar mensaje | Llamados a la acción |
| Landing | Terms and Conditions · Privacy Policy | Términos y condiciones · Política de privacidad | Documentos legales en el pie de página |
| App | Home · Zones · Alerts · History · Settings | Inicio · Zonas · Alertas · Historial · Ajustes | Destinos de la barra de navegación |
| App | Safe · Warning · Critical | Seguro · Advertencia · Crítico | Estados de zona y estado general |
| App | Confirm · Call contact · Call 116 · Mark as false alarm · Mark as resolved | Confirmar · Llamar al contacto · Llamar al 116 · Marcar como falsa alarma · Marcar como resuelto | Acciones sobre alertas e incidentes |
| App | Add sensor · Scan the sensor QR code · Save sensor | Agregar sensor · Escanear el QR del sensor · Guardar sensor | Registro de sensores |
| App | Safety thresholds · Emergency contact · Language · Plan · Sign out | Umbrales de seguridad · Contacto de emergencia · Idioma · Plan · Cerrar sesión | Grupos de configuración |

#### 3.1.2.3. SEO Tags and Meta Tags

**Landing Page**

```html
<html lang="en">
<title>SmartGas | Real-time gas leak and fire prevention for homes and restaurants</title>
<meta name="description" content="SmartGas monitors gas and temperature in your kitchen in real time and sends instant alerts to your phone. Plans for homes and restaurants in Peru.">
<meta name="keywords" content="gas leak detector, LPG safety, kitchen fire prevention, smart home safety, restaurant safety, IoT gas sensor, Peru">
<meta name="author" content="FireSecure">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta property="og:title" content="SmartGas · Your kitchen safety, always in real time">
<meta property="og:description" content="Real-time monitoring, push alerts and guided emergency response.">
<link rel="alternate" hreflang="es-419" href="https://smartgas-landingpage.netlify.app/?lang=es">
```

**Aplicaciones móviles (App Store Optimization)**

| Elemento ASO | Valor (en_US) | Valor (es_419) |
|:--|:--|:--|
| App title | SmartGas: Gas Leak Alerts | SmartGas: Alertas de fuga de gas |
| App subtitle / short description | Kitchen safety in real time | Seguridad de tu cocina en tiempo real |
| App keywords | gas leak, LPG, gas detector, fire alarm, kitchen safety, smart home, restaurant safety | fuga de gas, GLP, detector de gas, incendio, seguridad cocina, restaurante |
| App description | Monitor gas and temperature in every zone of your kitchen, get high-priority push alerts with step-by-step guidance, register sensors by scanning their QR code and keep a history of every incident. | Monitorea el gas y la temperatura de cada zona de tu cocina, recibe alertas push con una guía paso a paso, registra sensores escaneando su QR y conserva el historial de incidentes. |
| Category | House & Home (Google Play) / Utilities (App Store) | Casa y hogar / Utilidades |

#### 3.1.2.4. Searching Systems

- **Landing Page:** al ser de una sola página, no requiere buscador; la navegación por anclas del menú cumple esa función.
- **Zones:** búsqueda por nombre de zona o de sensor y Filter Chips por estado (All, Safe, Warning, Critical). Los resultados se muestran como tarjetas con el estado y los valores actuales.
- **Alerts:** filtros por estado (Active, Confirmed, All); los resultados se ordenan por severidad y luego por fecha.
- **History:** filtro por rango de fechas (Date Range Picker), por zona y por severidad, y la opción de ver solo las falsas alarmas. Los resultados se presentan en una lista cronológica con indicadores de resumen (incidentes, resueltos y tiempo promedio de respuesta). Si no hay coincidencias, se muestra un estado vacío con la opción de cambiar los filtros.
- **Add sensor:** en lugar de buscar el sensor, el usuario escanea su QR y la app completa el código y el tipo.

#### 3.1.2.5. Navigation Systems

- **Landing Page:** menú fijo en el encabezado (menú hamburguesa en móvil), navegación por desplazamiento entre secciones, llamados a la acción «Get the app» y «Contact us», y pie de página con accesos rápidos y documentos legales.
- **App móvil · navegación global:** Navigation Bar inferior con cinco destinos (Home, Zones, Alerts, History, Settings) y acceso al escáner QR y al perfil desde la barra superior del dashboard.
- **App móvil · navegación local:** navegación jerárquica con flecha de regreso (Zones → Zone detail → Sensor detail) implementada con Navigation Compose.
- **App móvil · navegación contextual:** las notificaciones push funcionan como *deep links* que abren directamente el detalle de la alerta; desde una alerta se navega al incidente.
- **Flujos secuenciales:** el registro de sensores y la respuesta a una alerta crítica se presentan como pasos, con una sola acción principal por pantalla.

### 3.1.3. Landing Page UI Design

El landing page traduce las decisiones de la arquitectura de información en un recorrido secuencial: primero comunica el problema y la propuesta de valor, luego muestra los beneficios y la app, y termina con los planes, el equipo y el contacto. Para este curso se reutiliza el landing page desarrollado en Aplicaciones Web y se actualiza con una nueva sección *Get the SmartGas app*, la sección de equipo con los integrantes actuales y la corrección de una característica: el apagado automático de válvulas se reemplaza por la respuesta guiada, porque el control de actuadores no forma parte del alcance.

#### 3.1.3.1. Landing Page Wireframe

**Desktop Web Browser.** Los wireframes de escritorio conservan la estructura del ciclo anterior: encabezado con logotipo, menú y selector de idioma; sección principal con imagen, titular, subtítulo y dos botones; bloques de tres columnas para beneficios y características; tres tarjetas de planes; cuadrícula del equipo; formulario de contacto y pie de página.

<table>
  <tr>
    <td align="center"><img alt="Portada" src="assets/26-Landing_Wireframe_Portada.png" width="380" /><br><em>Portada</em></td>
    <td align="center"><img alt="About us" src="assets/27-Landing_Wireframe_AboutUs.png" width="380" /><br><em>About us</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Benefits" src="assets/28-Landing_Wireframe_Benefits.png" width="380" /><br><em>Benefits</em></td>
    <td align="center"><img alt="Features" src="assets/29-Landing_Wireframe_Features.png" width="380" /><br><em>Features</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Plans" src="assets/30-Landing_Wireframe_Plans.png" width="380" /><br><em>Plans</em></td>
    <td align="center"><img alt="Team" src="assets/31-Landing_Wireframe_Team.png" width="380" /><br><em>Team</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Contact" src="assets/32-Landing_Wireframe_Contact.png" width="380" /><br><em>Contact</em></td>
    <td align="center"><img alt="Footer" src="assets/33-Landing_Wireframe_Footer.png" width="380" /><br><em>Footer</em></td>
  </tr>
</table>

**Mobile Web Browser.** En móvil el contenido se reorganiza en una sola columna, el menú se convierte en un menú hamburguesa y los botones ocupan el ancho completo para facilitar el toque. La nueva sección *Get the app* coloca primero el texto y el botón de descarga y después las capturas de la app.

<div align="center">
  <img alt="Landing Page Wireframe Mobile" src="assets/34-Landing_Wireframe_Mobile.png" />
</div>

#### 3.1.3.2. Landing Page Mock-up

**Desktop Web Browser · versión actual.** El mock-up aplica la paleta, la tipografía Koulen en los titulares y la jerarquía visual definida en las guías de estilo.

<div align="center">
  <img alt="Landing Page Mock-up Desktop" src="assets/35-Landing_Mockup_Desktop.jpg" width="600" />
</div>

**Desktop Web Browser · secciones nuevas del TB1.** La sección *Get the SmartGas app* presenta los beneficios de la app, el botón de descarga y dos capturas reales de los mock-ups de la app; la sección *Our team* muestra a los integrantes actuales de FireSecure.

<div align="center">
  <img alt="Sección Get the SmartGas app" src="assets/36-Landing_Mockup_GetTheApp.png" />
  <br><br>
  <img alt="Sección Our team" src="assets/37-Landing_Mockup_OurTeam.png" />
</div>

**Mobile Web Browser.** El landing page en un navegador móvil de 390 px de ancho mantiene la legibilidad y el tamaño táctil de los botones.

<div align="center">
  <img alt="Landing Page Mock-up Mobile" src="assets/38-Landing_Mockup_Mobile.jpg" />
  <br><br>
  <img alt="Landing Page Mock-up Mobile · Get the app" src="assets/39-Landing_Mockup_Mobile_GetTheApp.png" width="300" />
</div>

### 3.1.4. Mobile Applications UX/UI Design

La app móvil se diseñó primero para Android (Sprints 1 y 2) y sus pantallas se reutilizarán en la app Flutter (Sprints 3 y 4). Los diseños usan como caso al restaurante de Helí Rodríguez (cuatro zonas y nueve sensores), porque cubre también los flujos de un hogar con una sola zona.

#### 3.1.4.1. Mobile Applications Wireframes

Los wireframes definen la estructura de cada pantalla sin color, para validar la jerarquía y la navegación antes del diseño visual. Aplican los principios de jerarquía (el estado general primero), proximidad (los valores de cada zona agrupados en una tarjeta), consistencia (la misma barra de navegación en los destinos principales) y diseño inclusivo (textos junto a los íconos y botones de ancho completo).

<table>
  <tr>
    <td align="center"><img alt="Sign in" src="assets/40-App_Wireframe_SignIn.png" width="200" /><br><em>Sign in</em></td>
    <td align="center"><img alt="Sign in · error" src="assets/41-App_Wireframe_SignIn_Error.png" width="200" /><br><em>Sign in · error</em></td>
    <td align="center"><img alt="Create account" src="assets/42-App_Wireframe_CreateAccount.png" width="200" /><br><em>Create account</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Home (dashboard)" src="assets/43-App_Wireframe_Home.png" width="200" /><br><em>Home (dashboard)</em></td>
    <td align="center"><img alt="Home sin conexión" src="assets/44-App_Wireframe_Home_Offline.png" width="200" /><br><em>Home sin conexión</em></td>
    <td align="center"><img alt="Zones" src="assets/45-App_Wireframe_Zones.png" width="200" /><br><em>Zones</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Zone detail" src="assets/46-App_Wireframe_ZoneDetail.png" width="200" /><br><em>Zone detail</em></td>
    <td align="center"><img alt="Sensor detail" src="assets/47-App_Wireframe_SensorDetail.png" width="200" /><br><em>Sensor detail</em></td>
    <td align="center"><img alt="Add sensor" src="assets/48-App_Wireframe_AddSensor.png" width="200" /><br><em>Add sensor</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Scan sensor QR" src="assets/49-App_Wireframe_ScanSensorQR.png" width="200" /><br><em>Scan sensor QR</em></td>
    <td align="center"><img alt="Push notification" src="assets/50-App_Wireframe_PushNotification.png" width="200" /><br><em>Push notification</em></td>
    <td align="center"><img alt="Alerts" src="assets/51-App_Wireframe_Alerts.png" width="200" /><br><em>Alerts</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Alert detail" src="assets/52-App_Wireframe_AlertDetail.png" width="200" /><br><em>Alert detail</em></td>
    <td align="center"><img alt="History" src="assets/53-App_Wireframe_History.png" width="200" /><br><em>History</em></td>
    <td align="center"><img alt="Incident detail" src="assets/54-App_Wireframe_IncidentDetail.png" width="200" /><br><em>Incident detail</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Settings" src="assets/55-App_Wireframe_Settings.png" width="200" /><br><em>Settings</em></td>
    <td align="center"><img alt="Plans" src="assets/56-App_Wireframe_Plans.png" width="200" /><br><em>Plans</em></td>
    <td></td>
  </tr>
</table>

- **Sign in / Create account:** formulario en una columna, mensaje de error debajo del campo y aceptación explícita de los términos y condiciones.
- **Home:** organización jerárquica: banner de estado general, tres indicadores, zonas más relevantes y clima exterior. La variante sin conexión agrega un aviso con la hora de la última actualización.
- **Zones, Zone detail y Sensor detail:** organización espacial por ambiente; cada tarjeta muestra estado, gas y temperatura, y el detalle agrega la tendencia con la línea del umbral.
- **Add sensor y Scan sensor QR:** flujo secuencial con la opción de escaneo destacada y el ingreso manual como alternativa.
- **Push notification, Alerts y Alert detail:** la notificación incluye acciones rápidas; el detalle presenta los valores medidos, la guía numerada y las acciones de emergencia.
- **History e Incident detail:** organización cronológica con filtros y una línea de tiempo del incidente.
- **Settings y Plans:** grupos de configuración y comparación de planes.

#### 3.1.4.2. Mobile Applications Wireflow Diagrams

Se elaboró un wireflow por cada *user goal* principal de los User Personas. Cada paso muestra el wireframe con el estado de la pantalla después de la interacción indicada en la flecha. Los wireflows parten de los *task flows* acordados por el equipo y sirven como base de los user flows.

**User goal 1 (María y Helí):** iniciar sesión y conocer en segundos el estado de seguridad de su cocina.

<div align="center">
  <img alt="Wireflow 1" src="assets/57-Wireflow_1_SignIn_Status.png" />
</div>

El usuario inicia sesión; si las credenciales son incorrectas, el mensaje aparece en la misma pantalla y puede corregirlas. Al ingresar, el dashboard muestra el estado general y, desde la barra de navegación, puede revisar todas sus zonas.

**User goal 2 (María y Helí):** responder a una alerta crítica de fuga de gas.

<div align="center">
  <img alt="Wireflow 2" src="assets/58-Wireflow_2_Critical_Alert.png" />
</div>

La notificación push abre el detalle de la alerta. El usuario confirma la recepción (o la marca como falsa alarma) y la alerta pasa a confirmada; luego puede revisar la línea de tiempo del incidente.

**User goal 3 (Helí):** registrar un nuevo sensor escaneando su código QR.

<div align="center">
  <img alt="Wireflow 3" src="assets/59-Wireflow_3_Register_Sensor_QR.png" width="600" />
</div>

Desde Zones, el usuario agrega un sensor, abre el escáner y, al leer el QR, vuelve al formulario con el código y el tipo completados. Al guardar, el sensor aparece en el detalle de la zona.

**User goal 4 (Helí):** revisar el historial y resolver un incidente.

<div align="center">
  <img alt="Wireflow 4" src="assets/60-Wireflow_4_History_Incident.png" />
</div>

**User goal 5 (María y Helí):** ajustar los umbrales, el idioma y el contacto de emergencia.

<div align="center">
  <img alt="Wireflow 5" src="assets/61-Wireflow_5_Settings.png" />
</div>

#### 3.1.4.3. Mobile Applications Mock-ups

Los mock-ups aplican el Design System de SmartGas sobre los wireframes: Material Design 3, tipografía Roboto, la paleta de marca, los colores semánticos de estado y los íconos Material Symbols Rounded. Todas las pantallas se muestran en inglés, idioma por defecto.

<table>
  <tr>
    <td align="center"><img alt="Sign in" src="assets/62-App_Mockup_SignIn.png" width="200" /><br><em>Sign in</em></td>
    <td align="center"><img alt="Sign in · error" src="assets/63-App_Mockup_SignIn_Error.png" width="200" /><br><em>Sign in · error</em></td>
    <td align="center"><img alt="Create account" src="assets/64-App_Mockup_CreateAccount.png" width="200" /><br><em>Create account</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Home (dashboard)" src="assets/65-App_Mockup_Home.png" width="200" /><br><em>Home (dashboard)</em></td>
    <td align="center"><img alt="Home sin conexión" src="assets/66-App_Mockup_Home_Offline.png" width="200" /><br><em>Home sin conexión</em></td>
    <td align="center"><img alt="Zones" src="assets/67-App_Mockup_Zones.png" width="200" /><br><em>Zones</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Zone detail" src="assets/68-App_Mockup_ZoneDetail.png" width="200" /><br><em>Zone detail</em></td>
    <td align="center"><img alt="Sensor detail" src="assets/69-App_Mockup_SensorDetail.png" width="200" /><br><em>Sensor detail</em></td>
    <td align="center"><img alt="Add sensor" src="assets/70-App_Mockup_AddSensor.png" width="200" /><br><em>Add sensor</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Scan sensor QR" src="assets/71-App_Mockup_ScanSensorQR.png" width="200" /><br><em>Scan sensor QR</em></td>
    <td align="center"><img alt="Push notification" src="assets/72-App_Mockup_PushNotification.png" width="200" /><br><em>Push notification</em></td>
    <td align="center"><img alt="Alerts" src="assets/73-App_Mockup_Alerts.png" width="200" /><br><em>Alerts</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Alert detail" src="assets/74-App_Mockup_AlertDetail.png" width="200" /><br><em>Alert detail</em></td>
    <td align="center"><img alt="History" src="assets/75-App_Mockup_History.png" width="200" /><br><em>History</em></td>
    <td align="center"><img alt="Incident detail" src="assets/76-App_Mockup_IncidentDetail.png" width="200" /><br><em>Incident detail</em></td>
  </tr>
  <tr>
    <td align="center"><img alt="Settings" src="assets/77-App_Mockup_Settings.png" width="200" /><br><em>Settings</em></td>
    <td align="center"><img alt="Plans" src="assets/78-App_Mockup_Plans.png" width="200" /><br><em>Plans</em></td>
    <td></td>
  </tr>
</table>

- La pantalla **Home** usa el color Safe en el banner solo cuando todas las zonas están seguras y siempre lo acompaña con texto e ícono.
- La pantalla **Alert detail** concentra el color Critical en el banner y en la acción «Call 116» para que la urgencia sea evidente sin saturar la pantalla; la acción principal, «Confirm I received it», usa el color Primary.
- La pantalla **Scan sensor QR** usa fondo oscuro para resaltar el visor y explica que la lectura ocurre en el dispositivo.
- La pantalla **Plans** muestra los precios en soles y marca el plan vigente con un borde de color Primary.

#### 3.1.4.4. Mobile Applications User Flow Diagrams

Los user flows se derivan de los wireflows y usan los mock-ups de cada pantalla. Representan la ruta esperada (*happy path*) y las rutas alternativas (*unhappy paths*, en rojo).

**User Flow 1 · User goal: iniciar sesión y conocer el estado de la cocina.** Si las credenciales son inválidas, la app muestra el error y permite reintentar; si no hay conexión, muestra el último estado guardado.

<div align="center">
  <img alt="User Flow 1" src="assets/79-UserFlow_1_SignIn_Status.png" />
</div>

**User Flow 2 · User goal: responder a una alerta crítica.** Si el usuario confirma que la fuga es real, puede llamar a su contacto o al 116 y luego seguir el incidente; si se trata de una falsa alarma, la marca como tal y el incidente se cierra.

<div align="center">
  <img alt="User Flow 2" src="assets/80-UserFlow_2_Critical_Alert.png" />
</div>

**User Flow 3 · User goal: registrar un sensor por QR.** Las rutas alternativas cubren el permiso de cámara denegado, un QR no válido y el límite de sensores del plan (respuesta 409 de los web services).

<div align="center">
  <img alt="User Flow 3" src="assets/81-UserFlow_3_Register_Sensor_QR.png" />
</div>

**User Flow 4 · User goal: revisar el historial y resolver un incidente.** Si los filtros no devuelven resultados, se muestra un estado vacío; si la causa aún no se corrige, el incidente queda como revisado con notas.

<div align="center">
  <img alt="User Flow 4" src="assets/82-UserFlow_4_History_Incident.png" />
</div>

**User Flow 5 · User goal: configurar los umbrales.** Si el valor está fuera del rango permitido, se muestra un mensaje de validación.

<div align="center">
  <img alt="User Flow 5" src="assets/83-UserFlow_5_Settings.png" />
</div>

#### 3.1.4.5. Mobile Applications Prototyping

El prototipo navegable se construyó en Figma a partir de los mock-ups, enlazando las pantallas según los paths de los user flows. El archivo contiene 17 pantallas y 73 zonas interactivas. Se usaron las interacciones *On tap → Navigate to* con la transición *Smart animate* para la navegación jerárquica, *Instant* para la barra de navegación y *Back* para la flecha de retroceso. Se definieron seis puntos de inicio (flows), uno por cada user flow de la sección 3.1.4.4 y uno adicional para el modo sin conexión.

<div align="center">
  <img alt="Prototipo en Figma" src="assets/84-Prototipo_Figma.png" width="600" />
</div>

| Elemento | Enlace |
|:--|:--|
| Prototipo en Figma | [Prototipo móvil de SmartGas](#) <!-- TODO: reemplazar # por el enlace del prototipo en Figma --> |
| Archivo de diseño | [SmartGas · Mobile Prototype](#) <!-- TODO: reemplazar # por el enlace del archivo de Figma --> |
