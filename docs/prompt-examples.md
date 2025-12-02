---
title: Prompt Examples
nav_order: 5
parent: Prompt Engineering
---

# Prompt Examples

## 🧩 Clasificación de Tipos de Prompting

### 1. **Prompting Instructivo (Instructional Prompting)**

📘 **Qué es:**

El más básico. Consiste en dar una **instrucción directa** que la IA debe ejecutar.

📋 **Ejemplo:**

“Resume este texto en tres puntos clave.”

“Traduce al inglés manteniendo el tono formal.”

💡 **Uso típico:** tareas simples, directas y sin ambigüedad.

### 2. **Prompting de Rol (Role Prompting)**

🎭 **Qué es:**

Le indica al modelo **adoptar una identidad o rol** para responder desde una perspectiva específica.

📋 **Ejemplo:**

“Actúa como un profesor de filosofía y explica el concepto de virtud en Aristóteles.”

“Eres un ingeniero de software con experiencia en .NET: sugiere buenas prácticas para migrar una librería.”

💡 **Ventaja:** mejora el tono, la precisión y la coherencia contextual de la respuesta.

### 3. **Prompting de Contexto (Contextual Prompting)**

🧠 **Qué es:**

Incluye información de fondo o ejemplos relevantes para guiar la respuesta.

📋 **Ejemplo:**

“Basándote en el siguiente documento técnico sobre el sistema de pagos, genera una lista de pruebas unitarias.”

💡 **Se usa en:** sistemas RAG, tareas analíticas o conversaciones largas donde el contexto cambia.

### 4. **Prompting de Ejemplo (Few-Shot / One-Shot / Zero-Shot)**

⚙️ **Qué es:**

Permite enseñar a la IA **por demostración**, mostrando ejemplos del formato o tipo de salida esperada.

📋 **Ejemplo Few-Shot:**

```
Ejemplo 1:
Entrada: “Hoy está lloviendo.”
Salida: “El clima es lluvioso.”

Ejemplo 2:
Entrada: “Hace sol.”
Salida: “El clima es soleado.”

Ahora:
Entrada: “Está nublado.”
Salida:

```

💡 **Uso típico:** entrenamiento implícito sin ajustar el modelo (muy usado en producción).

---

### 5. **Prompting de Razonamiento (Chain-of-Thought Prompting)**

🧩 **Qué es:**

Invita al modelo a **mostrar o seguir un proceso de razonamiento paso a paso**, mejorando la precisión lógica.

📋 **Ejemplo:**

> “Razona paso a paso antes de dar la respuesta final.”
> 
> 
> “Explica cómo llegaste a esa conclusión.”
> 

💡 **Ventaja:** mejora decisiones complejas (cálculos, inferencias, diagnósticos, etc.).

---

### 6. **Prompting de Reflexión o Autoevaluación (Self-Reflective Prompting)**

🔍 **Qué es:**

Pide al modelo **revisar o evaluar su propia respuesta**, corrigiendo errores o mejorando claridad.

📋 **Ejemplo:**

> “Vuelve a leer tu respuesta y verifica si todos los argumentos tienen evidencia lógica.”
> 
> 
> “Reescribe tu respuesta de forma más concisa y formal.”
> 

💡 **Uso avanzado:** mejora la calidad sin intervención humana directa.

---

### 7. **Prompting Jerárquico o por Etapas (Step-by-Step / Multi-Turn Prompting)**

🏗️ **Qué es:**

Divide una tarea compleja en **subtareas secuenciales**, cada una con su propio objetivo.

📋 **Ejemplo:**

1. “Primero identifica las entidades clave del texto.”
2. “Luego clasifica cada entidad según su función.”
3. “Finalmente genera un resumen estructurado.”

💡 **Ideal para:** agentes autónomos o cadenas de pensamiento estructuradas.

---

### 8. **Prompting de Formato (Structured Output Prompting)**

📊 **Qué es:**

Define explícitamente el **formato de salida**, útil para integraciones con sistemas o bases de datos.

📋 **Ejemplo:**

> “Devuelve la respuesta en formato JSON con los campos titulo, descripcion, prioridad.”
> 

💡 **Uso típico:** en agentes que interactúan con APIs o sistemas backend.

---

### 9. **Prompting Socrático o Dialógico**

💬 **Qué es:**

El modelo responde **haciendo preguntas o guiando el pensamiento**, en lugar de dar una respuesta inmediata.

📋 **Ejemplo:**

> “Antes de resolver, ¿qué supuestos estás haciendo sobre los datos?”
> 
> 
> “¿Qué pasaría si cambiamos la variable independiente?”
> 

💡 **Se usa en:** enseñanza, razonamiento crítico y aprendizaje guiado.

---

### 10. **Prompting de Agentes (Tool-Augmented or Agentic Prompting)**

🧩 **Qué es:**

Extiende el prompting tradicional integrando **acciones o herramientas externas** (por ejemplo, llamadas a APIs, búsquedas web, RAG, etc.).

📋 **Ejemplo:**

> “Busca en la base de datos el registro más reciente y genera un resumen del estado de la transacción.”
> 
> 
> “Usa la herramienta `sql_query` para verificar los resultados antes de responder.”
> 

💡 **Uso avanzado:** en arquitecturas de *AI Agents* o sistemas autónomos basados en LLM.

| Tipo de Prompt | Propósito Principal | Complejidad |
| --- | --- | --- |
| Instructivo | Ejecutar una orden | 🟢 Baja |
| Rol | Controlar tono/perspectiva | 🟢 Media |
| Contexto | Incluir información relevante | 🟡 Media |
| Ejemplo (Few/One/Zero-Shot) | Enseñar formato o patrón | 🟡 Media |
| Razonamiento (CoT) | Mejorar lógica paso a paso | 🟠 Alta |
| Reflexión | Autoevaluar y corregir | 🟠 Alta |
| Jerárquico | Resolver por etapas | 🔵 Alta |
| Formato | Salida estructurada (JSON, tabla, etc.) | 🟢 Media |
| Socrático | Estimular pensamiento crítico | 🟠 Alta |
| Agente | Combinar IA + herramientas externas | 🔴 Muy alta |

### 🔹 5. Ejemplo ampliado (agente con parámetros dinámicos)

Podrías estructurar un prompt parametrizado así:

```
Actúa como un desarrollador senior en {lenguaje} especializado en {framework}.
Genera una función que {tarea_descripcion}.
Antes de mostrar el código, explica brevemente el razonamiento seguido.
Devuelve la respuesta en formato JSON con los campos "explicacion" y "codigo".

```

➡️ Con variables dinámicas (`{lenguaje}`, `{framework}`, `{tarea_descripcion}`), este *prompt* podría ser usado por un **agente generador de código**.

---

## 🧠 1. Qué es un *Developer Agent* en este contexto

Un **Developer Agent** es un agente de IA especializado en tareas de desarrollo que:

- Comprende instrucciones estructuradas (*prompting language*).
- Usa un modelo LLM para **razonar y generar código**.
- Puede **validar o evaluar** su propio resultado.
- Opcionalmente, se integra con herramientas (compiladores, linters, repositorios, etc.).

⚙️ 2. Arquitectura básica del agente (usando Semantic Kernel)

┌──────────────────────────────────────┐
│        Developer Agent (SK)          │
├──────────────────────────────────────┤
│ 1️⃣ Prompt estructurado (rol + tarea) │
│ 2️⃣ LLM (OpenAI / Azure / local)      │
│ 3️⃣ Validación o test del código       │
│ 4️⃣ Salida estructurada (JSON)        │
└──────────────────────────────────────┘

## 🧮 4. (Opcional) Validación automática del código generado

Puedes añadir un paso adicional en el flujo del agente:

- Compilar el código con Roslyn (C# Compiler API).
- Ejecutar tests automáticos.
- Pedirle al modelo una **auto-revisión** si falla.

Por ejemplo:

```csharp
var validationPrompt = kernel.CreateFunctionFromPrompt(
    "Evalúa el siguiente código y sugiere mejoras si hay errores o malas prácticas:\n\n{{codigo}}");

var validation = await kernel.InvokeAsync(validationPrompt, new() { ["codigo"] = codigo });
Console.WriteLine("\n🔍 Evaluación automática:\n" + validation);

```

Ejemplo de Markdown:

![{15CD2AA5-39C2-48A0-A43B-1C8947242218}.png](assets/images/prompting/15CD2AA5-39C2-48A0-A43B-1C8947242218.png)

![{047C9087-1773-4855-81D7-8F9838DF6845}.png](assets/images/prompting/047C9087-1773-4855-81D7-8F9838DF6845.png)

![{2DC10674-339C-419C-A18D-E2FA94B49928}.png](assets/images/prompting/2DC10674-339C-419C-A18D-E2FA94B49928.png)