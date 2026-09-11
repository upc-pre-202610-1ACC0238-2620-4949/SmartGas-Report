# Capítulo II: Requirements Development and Software Solution Design

## 2.1. Competidores

### 2.1.1. Análisis competitivo

| Características           | Google Nest Protect                                     | Kidde                                                | Tyco SimplexGrinnell                                      | SmartGas                                                                                          |
|:--------------------------|:--------------------------------------------------------|:-----------------------------------------------------|:----------------------------------------------------------|:--------------------------------------------------------------------------------------------------|
| **Perfil del Competidor** | Ecosistema inteligente cerrado de alta gama.            | Líder en alarmas locales de bajo costo.              | Sistema industrial corporativo especializado.             | **Plataforma SaaS de monitoreo preventivo con arquitectura orientada a servicios (SOA).**         |
| **Mercado Objetivo**      | Hogares con alta conectividad y presupuesto.            | Familias y pequeños comercios locales.               | Grandes corporaciones y sector industrial.                | Hogares urbanos y restaurantes en Perú.                                                           |
| **Ventaja Competitiva**   | Integración total con Google Home y smartphones.        | Reconocimiento de marca y bajo costo de adquisición. | Alta robustez y certificaciones de seguridad industrial.  | **Monitoreo remoto vía App Móvil (nativa/multiplataforma) y notificaciones push en tiempo real.** |
| **Fortalezas**            | Ecosistema digital sólido y actualizaciones constantes. | Disponibilidad masiva y sin pagos de suscripción.    | Soluciones integrales para entornos de alta complejidad.  | **Arquitectura SOA escalable, Backend en C# y una app móvil de alta usabilidad.**                 |
| **Debilidades**           | Dependencia de hardware propietario y costo elevado.    | Carece de conectividad remota y gestión de datos.    | Instalaciones complejas e interfaces de usuario cerradas. | Marca nueva en el mercado con necesidad de validación inicial.                                    |

### 2.1.2. Estrategias y tácticas frente a competidores

**Fortalezas: Enfoque especializado en monitoreo preventivo y arquitectura SOA**
La startup FireSecure se diferencia de competidores como Google Nest Protect y Tyco al desarrollar SmartGas, una app móvil que no depende de ecosistemas cerrados. A diferencia de Kidde, que ofrece hardware analógico, SmartGas utiliza una arquitectura orientada a servicios (SOA) en C# que permite el procesamiento de telemetría en la nube, visualización móvil nativa/multiplataforma y un sistema de alertas proactivo.

**Táctica:**
Posicionar a SmartGas en el mercado como la solución que democratiza la seguridad inteligente, permitiendo a los usuarios monitorear sus instalaciones desde su smartphone sin la complejidad de sistemas industriales ni el costo de hardware de gama alta.

**Debilidades: Startup en etapa temprana con necesidad de validación**
Al ser una empresa nueva, FireSecure no cuenta aún con la trayectoria de marca de Google ni las certificaciones masivas de Tyco. Esto puede generar dudas en el segmento comercial (restaurantes) respecto a la fiabilidad a largo plazo de la plataforma SmartGas.

**Táctica:**
Ejecutar programas piloto de SmartGas en restaurantes locales de Lima (como en Jesús María) para recolectar métricas de desempeño y testimonios. Estos casos de éxito servirán como validación técnica para demostrar la robustez del backend y de la app móvil frente a situaciones reales.

**Oportunidades: Necesidad de digitalización en el sector residencial y culinario peruano**
Existe un vacío en el mercado local donde los sistemas de seguridad son locales o muy costosos. SmartGas tiene la oportunidad de capturar este nicho ofreciendo una solución que se integra con dispositivos IoT accesibles, algo que los competidores internacionales no han adaptado al contexto económico del Perú.

**Táctica:**
Enfocar los esfuerzos de marketing de FireSecure en la "Prevención Basada en Datos", ofreciendo no solo la alarma, sino el historial de eventos y reportes estadísticos de SmartGas para que los administradores de restaurantes puedan tomar decisiones informadas sobre sus operaciones desde la app móvil.

**Amenazas: Competidores con mayores recursos y capacidad de réplica**
Empresas consolidadas podrían intentar lanzar versiones simplificadas de sus productos si perciben el crecimiento de FireSecure. Además, el ingreso de soluciones genéricas de bajo costo podría presionar los precios de suscripción de SmartGas.

**Táctica:**
Mantener una ventaja competitiva a través de la innovación ágil en el software. FireSecure debe aprovechar su arquitectura SOA para integrar rápidamente nuevas funcionalidades en SmartGas basadas en el feedback de los usuarios locales y ofrecer un soporte técnico en español directo y especializado, algo que Google o Kidde no priorizan en la región.

## 2.2. Entrevistas.

### 2.2.1. Diseño de entrevistas

### 2.2.2. Registro de entrevistas

### 2.2.3. Análisis de entrevistas

## 2.3. Needfinding

### 2.3.1. User Personas

### 2.3.2. User Task Matrix

### 2.3.3. User Journey Mapping

### 2.3.4. Empathy Mapping

### 2.3.5. Big Picture EventStorming

### 2.3.6. Ubiquitous Language

## 2.4. Requirements specification

### 2.4.1. User Stories

### 2.4.2. Impact Mapping

### 2.4.3. Product Backlog

## 2.5. Strategic-Level Domain-Driven Design

### 2.5.1. EventStorming

#### 2.5.1.1. Candidate Context Discovery

#### 2.5.1.2. Domain Message Flows Modeling

#### 2.5.1.3. Bounded Context Canvases

### 2.5.2. Context Mapping

### 2.5.3. Software Architecture

#### 2.5.3.1. Software Architecture Context Level Diagrams

#### 2.5.3.2. Software Architecture Container Level Diagrams

#### 2.5.3.3. Software Architecture Deployment Diagrams

## 2.6. Tactical-Level Domain-Driven Design

### 2.6.1. Bounded Context: IAM (Identity and Access Management)

#### 2.6.1.1. Domain Layer

#### 2.6.1.2. Interface Layer

#### 2.6.1.3. Application Layer

#### 2.6.1.4. Infrastructure Layer

#### 2.6.1.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.1.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.1.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.1.6.2. Bounded Context Database Design Diagram

### 2.6.2. Bounded Context: Kitchen Monitoring

#### 2.6.2.1. Domain Layer

#### 2.6.2.2. Interface Layer

#### 2.6.2.3. Application Layer

#### 2.6.2.4. Infrastructure Layer

#### 2.6.2.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.2.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.2.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.2.6.2. Bounded Context Database Design Diagram

### 2.6.3. Bounded Context: Incident Detection

#### 2.6.3.1. Domain Layer

#### 2.6.3.2. Interface Layer

#### 2.6.3.3. Application Layer

#### 2.6.3.4. Infrastructure Layer

#### 2.6.3.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.3.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.3.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.3.6.2. Bounded Context Database Design Diagram

### 2.6.4. Bounded Context: Incident Prevention & Notification

#### 2.6.4.1. Domain Layer

#### 2.6.4.2. Interface Layer

#### 2.6.4.3. Application Layer

#### 2.6.4.4. Infrastructure Layer

#### 2.6.4.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.4.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.4.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.4.6.2. Bounded Context Database Design Diagram

### 2.6.5. Bounded Context: Post-Incident Procedures

#### 2.6.5.1. Domain Layer

#### 2.6.5.2. Interface Layer

#### 2.6.5.3. Application Layer

#### 2.6.5.4. Infrastructure Layer

#### 2.6.5.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.5.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.5.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.5.6.2. Bounded Context Database Design Diagram

### 2.6.6. Bounded Context: Payment Management

#### 2.6.6.1. Domain Layer

#### 2.6.6.2. Interface Layer

#### 2.6.6.3. Application Layer

#### 2.6.6.4. Infrastructure Layer

#### 2.6.6.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.6.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.6.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.6.6.2. Bounded Context Database Design Diagram

### 2.6.7. Bounded Context: Dashboard / Shared

#### 2.6.7.1. Domain Layer

#### 2.6.7.2. Interface Layer

#### 2.6.7.3. Application Layer

#### 2.6.7.4. Infrastructure Layer

#### 2.6.7.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.7.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.7.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.7.6.2. Bounded Context Database Design Diagram

