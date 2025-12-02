# RAG con Prompt Language

## Buenas prácticas de RAG para agentes que consumen APIs externas

**Ingesta & chunking**

- Preprocesa formatos comunes (OpenAPI/Swagger, Postman, Markdown, PDF).
- Divide en **chunks de ~500–1,000 tokens** con **overlap 50–100**; separa por secciones lógicas (por endpoint, por recurso, por error codes).
- Guarda **metadata** útil: `api=BancoX`, `version=v3.2`, `tipo=openapi`, `fecha=2025-10-12`.

**Estrategias de recuperación**

- **Híbrida** (BM25 + embeddings) cuando tengas muchos términos exactos (nombres de campos/paths).
- **Re-rank** (reordenado) para elevar pasajes con ejemplos de código o secciones “Request/Response”.
- En el prompt: pide **citas** (archivo + sección) y obliga al modelo a **no inventar endpoints** si no están en las fuentes.

**Ciclo de mejora continua**

- **Evaluación**: crea un set de preguntas exigentes (versiones, edge-cases, códigos de error) y mide *precision@k*, *hit rate*, y *factualidad con cita*.
- **Feedback loop**: captura fallos de generación (p. ej., endpoint incorrecto) → añade/actualiza docs → reindexa.
- **Versionado**: cuando cambie la API externa, sube el **nuevo OpenAPI** y marca la versión en metadata; puedes mantener versiones en paralelo y filtrar por `version` según rama o entorno.
- **Guardrails**: valida que el código generado llama **únicamente** a endpoints citados. Si falta contexto, el agente debe pedir la fuente o rechazar la acción.

**Seguridad & permisos**

- Evita subir secretos (usa variables/VAULT).
- En ejemplos de código, usa **placeholders** (`API_KEY`) y añade políticas de rotación/autenticación.
- Si el proveedor expone *rate limits*, incluye *retry/backoff* y manejo de *429/5xx* en los templates de código.

![{A1E7BD0D-AA22-4E71-80A8-5203D2006A67}.png](A1E7BD0D-AA22-4E71-80A8-5203D2006A67.png)

![{4F8B4BA8-E4B9-437B-B6C2-F2181D7D78C9}.png](4F8B4BA8-E4B9-437B-B6C2-F2181D7D78C9.png)

---

En un archivo yaml

![{95624AEC-CD2C-4D91-90CE-D7C606C20DE6}.png](95624AEC-CD2C-4D91-90CE-D7C606C20DE6.png)

### ===========================

### Buenas prácticas / notas importantes

### ===========================

1. **Secrets**: NO pongas API keys ni contraseñas en archivos `appsettings.*.json` para QA/Prod. Usa AWS Secrets Manager o variables de entorno proporcionadas por la plataforma de despliegue (ECS task definitions, Kubernetes secrets, etc.).
2. **CloudWatch**: La sink de Serilog para CloudWatch requiere crear el LogGroup (o que la política lo permita). Asegura IAM role/creds con permisos de `logs:PutLogEvents` y relacionados.
3. **Escalabilidad**: Para alto volumen de llamadas, segmenta por ciudad, usa colas y workers paralelos con throttling.
4. **Resiliencia**: Ajusta políticas de Polly (retry/circuit-breaker) según SLA del servicio externo.
5. **Testing**: Agrega tests unitarios para `WeatherProcessor` y `OpenWeatherClient` (mockeando HttpClient).
6. **Observabilidad adicional**: Considera agregar OpenTelemetry traces y métricas para latencia y errores.

---

### ===========================

### Siguientes pasos recomendados (acciones concretas)

### ===========================

1. Copiar la estructura y archivos a tu repo en Cursor.
2. Ejecutar localmente en `Development` y validar integraciones (migraciones, DB local).
3. Configurar AWS IAM role y SecretsManager para QA/Prod.
4. En Cursor, pide:
    - “Genera pruebas unitarias para WeatherProcessor con xUnit y Moq.”
    - “Refactoriza OpenWeatherClient para usar Typed HttpClient y mejorar testabilidad.”
    - “Añade HealthChecks y un endpoint /health para la API.”

---

¿Quieres que **genere los archivos en un ZIP descargable** ahora (que puedas abrir directamente en Cursor), o prefieres que empiece por una parte concreta (por ejemplo: generar tests unitarios para `WeatherProcessor` y `OpenWeatherClient`)?