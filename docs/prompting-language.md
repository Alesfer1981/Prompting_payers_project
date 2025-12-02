# Prompting language

### **Prompting language”** o **lenguaje de instrucciones estructuradas para IA**

Es un concepto clave en la interacción moderna con modelos de lenguaje (LLM).

### 🔹 Definición Ampliada

---

El **lenguaje de instrucciones estructuradas para IA**, también llamado **prompting language**, es un conjunto de **convenciones, estructuras y estrategias lingüísticas** diseñadas para comunicarse eficazmente con modelos de lenguaje o agentes inteligentes.

Su propósito principal es **traducir la intención humana en comandos o instrucciones comprensibles y procesables por la IA**, optimizando la calidad, relevancia y coherencia de las respuestas generadas.

---

### 🔹 Características Principales

1. **Estructurado pero flexible:**
    
    Aunque no tiene una gramática formal como los lenguajes de programación, sigue patrones estructurados (roles, contexto, formato de salida, restricciones, etc.).
    
2. **Basado en contexto:**
    
    La IA interpreta el significado de las instrucciones considerando el contexto anterior, los ejemplos y las condiciones definidas en el prompt.
    
3. **Orientado a objetivos:**
    
    Cada instrucción busca un resultado concreto: generar texto, analizar datos, ejecutar una acción o razonar sobre información.
    
4. **Multimodal y extensible:**
    
    Puede incluir texto, variables, fragmentos de código o incluso referencias visuales (en modelos que aceptan imágenes o audio).
    

---

### 🔹 Ejemplo simple

```
Actúa como un asesor financiero experto.
Analiza los siguientes datos de gastos y sugiere tres estrategias de ahorro:
- Alimentación: 500 USD
- Transporte: 200 USD
- Ocio: 150 USD
Devuelve la respuesta en formato de tabla con una columna adicional para “Impacto estimado”.

```

➡️ Aquí se observa la **estructura del prompting language**:

- Rol asignado (“actúa como…”).
- Contexto de la tarea (análisis financiero).
- Datos de entrada.
- Reglas de formato (tabla, columna adicional).

---

### 🔹 Relación con el *prompt engineering*

El **prompting language** es la *“gramática” o el medio de comunicación*,

mientras que el **prompt engineering** es la *disciplina o práctica* de diseñar, probar y optimizar esas instrucciones.

En otras palabras:

> 🔸 Prompting language = el idioma.
> 
> 
> 🔸 *Prompt engineering* = la ingeniería que lo usa para lograr resultados óptimos.
> 

---

## **Ejemplo de simbología y estructura**

- ##: Encabezado principal o inicio de una instrucción.
- ###: Subtarea, sección o paso dentro del flujo de instrucciones.
- *Bold (negrita, como **Why this matters:)**: Indicación de elementos importantes para llamar la atención del modelo o usuario.
- cursivas (*texto*)
- Otras etiquetas: Pueden incluir listas, estándares de formato y anotaciones que ayudan a delimitar el contexto y las acciones a seguir por los agentes de IA.

---

## ✅ Cómo usarla

Puedes pegar esta plantilla en:

- Un **agente LLM** (como ChatGPT, Semantic Kernel, LangChain, Copilot Agent, etc.).
- O incluirla como **archivo de prompt base** (`prompts/CreateProject.txt`) dentro de un pipeline de generación automática de proyectos.

---

*markdown* 

# 🧠 Prompt Inicial - Proyecto Empresarial en .NET 8 (Worker + API Gateway)

### 📌 Contexto del Proyecto

Descripción general del sistema y objetivo.

Necesito que actúes como **arquitecto senior de software en .NET** y generes un proyecto completo con una arquitectura limpia y modular.

El sistema debe ejecutar un **servicio en segundo plano (Worker Service)** que consulta periódicamente una **API externa de clima (OpenWeatherMap)** y almacena los resultados en una base de datos **SQL Server**.

El servicio formará parte de un entorno mayor de microservicios y debe estar preparado para **despliegue en AWS ECS o EC2**, con **monitorización centralizada vía CloudWatch** y **parametrización de ambientes (Development, QA, Production)**.

---

### 🎯 Requisitos funcionales

Qué debe hacer el sistema, módulos principales y flujos esperados.

1. Llamar cada 5 minutos a la API externa de clima.
2. Guardar los datos del clima (temperatura, humedad, presión, ciudad, fecha) en una tabla.
3. Ofrecer una API interna (REST, [ASP.NET](http://asp.net/) Core Minimal API) para consultar los últimos registros del clima desde el cliente.
4. Manejar reintentos automáticos y fallos temporales (Polly).
5. Soportar inyección de dependencias para servicios, repositorios y configuraciones.

---

### 🧩 Requisitos técnicos

Lenguaje, framework, arquitectura, patrones, librerías deseadas.

- **Lenguaje**: C# (.NET 8)
- **Tipo de proyecto**: Worker Service + Minimal API Gateway en la misma solución.
- **Arquitectura**: Limpia (Clean Architecture) con capas:
    - Application
    - Infrastructure
    - Domain
    - Worker
    - API
- **Patrones**: Repository Pattern, Dependency Injection, Config Pattern, Logging Middleware.
- **ORM**: Entity Framework Core 8.
- **HTTP Client Resiliente**: Polly con manejo de circuit breaker y reintentos.
- **Configuración**: `IOptions<T>` pattern para parámetros de entorno.

---

### 🗄️ Base de Datos

Modelo relacional, conexión, entidades clave, acceso y ORM.

- **Gestor**: Microsoft SQL Server.
- **Conexión**: desde cadena de conexión parametrizada (por ambiente).
- **Entidades principales**:
    - `WeatherRecord`: Id, City, Temperature, Humidity, Pressure, DateRecorded.
    - `EnvironmentConfig`: EnvironmentName, ApiKey, ApiBaseUrl, RetryPolicy.
- **Migraciones**: habilitadas con EF Core Migrations.

---

### 🌐 API / Integraciones externas

Qué servicios se consumirán, autenticación, frecuencia, manejo de errores.

- **Servicio externo**: OpenWeatherMap API.
- **URL base**: configurable por ambiente (via `appsettings.{env}.json`).
- **Autenticación**: por API Key almacenada en variable de entorno.
- **Frecuencia de ejecución**: 5 minutos entre llamadas.
- **Manejo de errores**: Retrys exponenciales + circuit breaker con Polly.

---

### ☁️ Logging y observabilidad

Dónde y cómo registrar logs, niveles, formatos, servicios (p.ej. CloudWatch, Serilog).

- **Proveedor**: Serilog.
- **Destino**: AWS CloudWatch Logs.
- **Configuración**:
    - Nivel mínimo: Information.
    - En Development: Consola + Archivo local.
    - En QA/Prod: CloudWatch.
- **Formato**: JSON estructurado.
- **Integración**: configuración central en `Logging/SerilogConfig.cs`.

--- 

### ⚙️ Configuración de entornos

Cómo separar QA, Development y Production. Uso de variables de entorno, configuración, secrets.

Cada entorno tendrá su propio archivo de configuración:

- `appsettings.Development.json`
- `appsettings.QA.json`
- `appsettings.Production.json`

---

### 🧰 Entregables esperados

Estructura de carpetas, archivos principales, configuración inicial, instrucciones de ejecución.

- Solución `.sln` con los siguientes proyectos:
    - `WeatherWorker.Domain`
    - `WeatherWorker.Infrastructure`
    - `WeatherWorker.Application`
    - `WeatherWorker.Worker`
    - `WeatherWorker.API`
- Archivos `.csproj` completos con dependencias requeridas.
- `appsettings` para cada ambiente.
- Ejemplo de migración inicial para crear la tabla `WeatherRecords`.
- `Dockerfile` y `docker-compose.yml` con soporte multienv.
- Instrucciones para ejecutar localmente (`dotnet run --environment Development`).

---

### 🧠 Estilo de código y estándares

Convenciones de nombres, principios SOLID, dependencia de inyección, etc.

- Cumplir principios **SOLID**.
- Uso de **async/await** y `CancellationToken` en todos los métodos.
- Nombrado PascalCase para clases y métodos.
- Propiedades con `init` cuando aplique.
- Interfaces con prefijo `I`.
- Comentarios XML Summary en métodos públicos.

---

### 🧾 Output deseado

Formato en que debe entregarse el código (archivos, ZIP, o texto plano por archivo).

1. Entrega el proyecto en formato **estructura de carpetas y archivos** con el código fuente por archivo.
2. Incluye fragmentos de los archivos `.csproj`, `appsettings.json`, y `Program.cs`.
3. No uses texto plano concatenado: entrega cada archivo con su título y contenido separado.
4. Finaliza indicando cómo ejecutar el proyecto localmente y cómo preparar variables de entorno para QA y Production.

---

[Context Enginnering](Context%20Enginnering%202b2c2187ea1280528aeae31606e8001a.md)

[Prompt Examples](Prompt%20Examples%20293c2187ea12806e91a0ceb83111deb4.md)

[RAG con Prompt Language](RAG%20con%20Prompt%20Language%202a4c2187ea1280e58c07cf335a1601dc.md)

![{0D61712F-7740-4771-B2AB-B74101B95AB7}.png](0D61712F-7740-4771-B2AB-B74101B95AB7.png)

![{4F4F8F95-FF50-4CCE-9C60-61143FCF4155}.png](4F4F8F95-FF50-4CCE-9C60-61143FCF4155.png)

ACE: Agent Context Engineering ⇒ Otro nuevo?