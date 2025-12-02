# RAG (Retrieval Augmented Generation)

Augmentation (Aumento)

Is the process of enhancing large language models (LLMs) by incorporating additional information from external knowledge sources. This enables the LLMs to generate more accurate and context-aware answers, while also reducing hallucinations.

RAG bridges the gap between retrieval-based and generative AI models by providing more informed answers by retrieving context from external knowledge bases.

RAG systems combine the power of **Large Language Models (LLMs)** with external knowledge retrieval, allowing chatbots and AI applications to provide contextually rich and accurate responses.

![{2566ACAA-F537-4CF5-A7A7-B9E05348FC11}.png](assets/images/2566ACAA-F537-4CF5-A7A7-B9E05348FC11.png)

Este es el modelo tradicional de comunicación con un sistema LLM:

![{D1F97EBE-3508-4367-857E-256177BC8B79}.png](assets/images/D1F97EBE-3508-4367-857E-256177BC8B79.png)

Aqui se representa el uso del RAG como complemento al sistema LLM original:

![{F4644A56-BCF7-482E-ADEA-8454DD54DC24}.png](assets/images/F4644A56-BCF7-482E-ADEA-8454DD54DC24.png)

RAG architecture comprises of two main components:

**Indexing:** The proprietary or external data is ingested via a data pipeline, and the data acquired in this manner is subsequently indexed.

The process of indexing is carried out in three stages:

1. Document loaders are used to load the data.
2. Larger documents are partitioned into smaller fragments or chunks.
3. These chunks are preserved utilizing an embedding model and vector database. ⇒ DEFINITION: Conectar una base vectorial real (como **FAISS**, [**Chroma**](https://docs.trychroma.com/docs/overview/getting-started) o [**Weaviate](https://medium.com/data-science/getting-started-with-weaviate-a-beginners-guide-to-search-with-vector-databases-14bbb9285839) [tutorial](https://docs.weaviate.io/weaviate/quickstart)**)

![{C371EE97-BAFA-457E-9947-AE84A4A401D9}.png](assets/images/C371EE97-BAFA-457E-9947-AE84A4A401D9.png)

The latest information can be incorporated into the RAG architecture in real-time:

![{B91FFEFC-83E9-4CE9-92D1-2ED46472BFB6}.png](assets/images/B91FFEFC-83E9-4CE9-92D1-2ED46472BFB6.png)

Typical workflow of RAG:

![image.png](assets/images/image%208.png)

**Embeding model:**

Un **embedding model** (modelo de incrustación) es un tipo de modelo de IA que convierte datos en números (vectores) para que sean más fáciles de procesar por una computadora.

![{754C4057-D722-4198-B8FE-6577C51540B6}.png](assets/images/754C4057-D722-4198-B8FE-6577C51540B6.png)

[aqui](https://medium.com/@nay1228/embedding-models-a-comprehensive-guide-for-beginners-to-experts-0cfc11d449f1)

### 📌 **Explicación sencilla:**

- Un embedding model toma palabras, imágenes o cualquier otro tipo de información y las transforma en **vectores numéricos** en un espacio matemático.
- Elementos similares se representan con números que están cerca entre sí.
- Esto permite que la IA entienda relaciones entre palabras, frases o conceptos sin que sean exactamente iguales.

### 🔍 **Ejemplo práctico:**

Imagina que tienes las palabras **"perro"**, **"gato"**, **"automóvil"** y **"camión"**.

Si usamos un modelo de embeddings, nos podría asignar estos números (vectores simplificados para el ejemplo):

- **perro → [0.1, 0.8]**
- **gato → [0.2, 0.85]**
- **automóvil → [0.9, 0.1]**
- **camión → [0.95, 0.15]**

Si miramos estos números, **perro y gato** están más cerca porque son animales, mientras que **automóvil y camión** están cerca entre sí porque son vehículos.

Este tipo de representación ayuda a las IA a hacer **búsquedas inteligentes**, completar frases o encontrar relaciones entre conceptos.

### 🔗 **Uso en IA y LLMs (por ejemplo en RAG)**

En **RAG (Retrieval-Augmented Generation)**, los embeddings se usan para buscar información relevante antes de generar respuestas.

Por ejemplo, si preguntas **"¿Cómo cuidar un cachorro?"**, el sistema usa embeddings para encontrar textos relacionados con **"perro", "mascota", "alimentación"**, aunque no uses esas palabras exactas.

📌 **En resumen:** **Un embedding model convierte información en números para que las IA puedan entender similitudes y relaciones entre conceptos de forma eficiente.**

¿Te quedó más claro? 😊

**Embedding Functions:** Embedding functions play a crucial role in the transformation of data chunks into numerical vectors

![image.png](assets/images/image%209.png)

![{D166866E-E488-4BA2-BFBC-9A4443F206FD}.png](assets/images/D166866E-E488-4BA2-BFBC-9A4443F206FD.png)

[here](https://machinelearningmastery.com/a-practical-guide-to-building-local-rag-applications-with-langchain/)

![{D8AFF803-FFDE-4483-9592-9460663B23FF}.png](assets/images/D8AFF803-FFDE-4483-9592-9460663B23FF.png)

![image.png](assets/images/image%2010.png)

Here are 8 RAG variants changing how we build with LLMs:

- 𝗦𝗶𝗺𝗽𝗹𝗲 𝗥𝗔𝗚 𝘄𝗶𝘁𝗵 𝗺𝗲𝗺𝗼𝗿𝘆 — add past interactions to make responses more grounded
- 𝗕𝗿𝗮𝗻𝗰𝗵𝗲𝗱 𝗥𝗔𝗚 — pull from APIs, databases, and knowledge graphs at once
- 𝗔𝗴𝗲𝗻𝘁𝗶𝗰 𝗥𝗔𝗚 — where an agent decides what to retrieve and when
- 𝗛𝘆𝗗𝗲 — generate hypothetical documents to guide more targeted lookups
- 𝗦𝗲𝗹𝗳-𝗥𝗔𝗚 — the system rephrases, self-grades, and reflects before generating
- 𝗔𝗱𝗮𝗽𝘁𝗶𝘃𝗲 𝗥𝗔𝗚 — chooses the best data source dynamically
- 𝗖𝗼𝗿𝗿𝗲𝗰𝘁𝗶𝘃𝗲 𝗥𝗔𝗚 (𝗖𝗥𝗔𝗚) — filters out noisy context using thresholds
- 𝗦𝗶𝗺𝗽𝗹𝗲 𝗥𝗔𝗚 — still a valid choice when your data is clean and static

I created this visual guide to help AI engineers, architects, and teams rethink what retrieval can (and should) do.

Because retrieval is no longer just “fetch and feed.”

It’s evolving into an intelligent layer that brings 𝗿𝗲𝗮𝘀𝗼𝗻𝗶𝗻𝗴, 𝗳𝗲𝗲𝗱𝗯𝗮𝗰𝗸, 𝗮𝗱𝗮𝗽𝘁𝗮𝗯𝗶𝗹𝗶𝘁𝘆, and 𝗰𝗼𝗻𝘁𝗿𝗼𝗹 into GenAI systems.

[**real-time RAG](https://qatalog.com/blog/post/real-time-rag/#what-is-realtime-rag):** Real-Time RAG, also known as No-Index RAG, eliminates the need to index data. Instead, it performs searches directly through live data sources using each platform's search API to retrieve the most accurate and up-to-date information while minimizing data security risks and reducing maintenance costs.

Real-Time RAG can be misleading because all RAG systems process queries in real-time. What makes our approach unique is that we access data directly from the source, retrieving information the instant it's created, rather than relying on pre-indexed copies of data.

RAG - [3 tecnicas de transformacion optimizacion](https://dev.to/jamesli/in-depth-understanding-of-rag-query-transformation-optimization-multi-query-problem-decomposition-and-step-back-27jg) (Todas se pueden implementar con Python)

- Multi-query: The core idea of the Multi-Query Rewriting strategy is to improve retrieval recall by generating multiple queries from different perspectives.
- Problem decomposition: The Problem Decomposition strategy targets complex queries by breaking them down into multiple simpler sub-problems.
- Step-Back: The Step-Back strategy involves "thinking a step back" to re-examine the problem from a more abstract or fundamental level.

![{C3616D3B-319D-46B5-8518-BC4E4B82B1D4}.png](assets/images/C3616D3B-319D-46B5-8518-BC4E4B82B1D4.png)

[Agentic RAG](Agentic%20RAG%20289c2187ea12806c9659d89683c7d30a.md)
