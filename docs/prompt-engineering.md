---
title: Prompt Engineering
nav_order: 1
parent: Prompt Engineering
---

# Prompt Engineering

La **Ingeniería de Prompts** se refiere al proceso de diseñar, ajustar y optimizar las instrucciones o "prompts" que se le dan a un modelo de inteligencia artificial, como un modelo de lenguaje, para obtener los resultados más precisos, relevantes o creativos posibles.

What is a Prompt? 

A prompt is an input to a Generative AI model, that is used to guide its output. Prompts may consist of text, image, sound, or other media.

En el contexto de modelos de lenguaje como GPT, un "prompt" es el texto que se ingresa para generar una respuesta. La ingeniería de prompts implica:

1. **Selección de palabras y estructura:** Elegir cuidadosamente el vocabulario y la estructura gramatical para guiar al modelo de manera efectiva.
2. **Contexto y detalle:** Proporcionar suficiente contexto o detalles específicos para reducir la ambigüedad y mejorar la relevancia de la respuesta.
3. **Iteración y ajuste:** Experimentar con diferentes formulaciones del prompt, modificando su longitud, tono o estilo, hasta que el modelo produzca el tipo de salida deseada.

Esta disciplina se ha vuelto crucial en el desarrollo de aplicaciones de IA, donde los resultados pueden variar significativamente en función de cómo se plantea la solicitud al modelo.

### **Prompts:**

- Un prompt es una instrucción, pregunta o un texto que se utiliza para interactuar con sistemas de inteligencia artificial. Podríamos decir que **es como un comando**, con el que vas a pedirle a este sistema que realice una tarea concreta. Los prompts pueden ser desde una frase de pocas palabras hasta uno o varios párrafos, incluyendo otros contenidos como un texto.
- Por lo tanto, **es importante que los prompts tengan todo el contexto que necesitas** para obtener un resultado, y también que no tengan ambigüedades o dobles sentidos que puedan hacer que los algoritmos de una IA malinterpreten lo que le pides.
- Crear un prompt eficaz es tanto un arte como una ciencia. Es un arte porque requiere creatividad, intuición y un profundo conocimiento del lenguaje. Es una ciencia porque se basa en la mecánica de los modelos de IA a la hora de procesar y generar respuestas.

### Elementos clave de un prompt:

Veamos los elementos esenciales que conforman un buen prompt:

- **Instrucción.** Es la directriz principal del prompt que indica al modelo lo que debe hacer. Por ejemplo, "Resume el siguiente texto" ofrece una acción clara y específica.
- **Contexto.** Proporciona información adicional que ayuda al modelo a entender el marco general o los antecedentes. Por ejemplo, "Teniendo en cuenta la recesión económica, proporciona asesoramiento de inversión" establece un escenario claro para la respuesta.
- **Datos de entrada.** Son la información específica que el modelo debe procesar, ya sea un párrafo, números o una palabra.
- **Indicador de salida.** Define el formato o estilo de respuesta deseado, siendo especialmente útil en representaciones de roles. Por ejemplo, "Reescribe la siguiente frase con el estilo de Shakespeare" establece una pauta estilística clara.

![image.png](image%2011.png)

[Five Principles of Prompting](five-principles-of-prompting.md)

### Curso youtube de Prompt Engineeting [here](https://www.youtube.com/playlist?list=PLhRXULtLjLtcT5Ig8f7V-_YAVw9mrjmQA)

### Prompt Engineering Techniques:

- in-context learning:
- Tree of Thoughts (ToT):
- Chain of Thoughts (CoT): Prompt de Cadena de pensamiento
- ReAct (Reason and Act): with this prompts direct both reasoning and action, enabling agents to explain their decisions and iteratively refine their approach.
- **Modular Reasoning** : with this well-designed prompts help break down complex problems into manageable sub-tasks, facilitating systematic and efficient execution.

**Iterative Retrieval-Augmented Generation (RAG)** : rely (confia) on adaptive prompts to repeatedly fetch (obtener repetidamente) relevant information, enhancing accuracy (mejorando la precisión)  and relevance throughout task completion (a lo largo de la finalización de la tarea) .

- RAG ([Generación Aumentada de Recuperación](https://www.oracle.com/es/artificial-intelligence/generative-ai/retrieval-augmented-generation-rag/)): Tomemos el ejemplo de una liga deportiva que desea que los aficionados y medios de comunicación puedan usar el chat para consultar datos y obtener respuesta a sus preguntas sobre los jugadores, los equipos, la historia y las reglas del deporte, así como las estadísticas y clasificaciones actuales. Un LLM general podría responder a preguntas sobre la historia y las reglas o tal vez describir el estadio de un equipo en particular. Sin embargo, no podría comentar el partido de ayer por la noche ni proporcionar información actualizada sobre la lesión de un deportista en particular porque no dispondría de esa información y, dado que se necesita una potencia de computación significativa para volver a entrenar un LLM, no es factible mantener el modelo al día. Además del LLM, grande y bastante estático, la liga deportiva posee o puede acceder a muchas otras fuentes de información, como bases de datos, almacenes de datos, documentos con biografías de los jugadores y fuentes de noticias que analizan cada partido en profundidad. La RAG permite a la [IA generativa](https://www.oracle.com/es/artificial-intelligence/generative-ai/what-is-generative-ai/) usar esta información. Ahora, el chat puede proporcionar información más oportuna, más adecuada al contexto y más precisa.
    
    En pocas palabras, la RAG ayuda a los LLM a proporcionar respuestas más idóneas.
    

### Ejemplos de uso de prompts:

- **Formatos:** Se pueden pedir formatos de salida en la respuesta como: CSV, Markdown, XML

![image.png](image%2012.png)

Indica que el parrafo ingresado debe ser resumido en formato .CSV

- **Role:** Se puede pude solicitar que adopte profesiones, oficios con niveles de expertisia para que exponga la respuesta deseada

- **Directivas:** Se pueden usar directivas para indicar una salida:
    
    ![image.png](image%2013.png)
    

- **Información adicional**: Si la indicacion/directiva es escribir un email, se puede incluir información como su nombre y su cargo para que el GenAI genere la firma del mensaje

[**Prompting language**](prompting-language.md)