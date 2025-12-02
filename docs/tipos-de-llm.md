---
title: Tipos de LLM
nav_order: 3
parent: LLM – Modelos de Lenguaje
---

# Tipos de LLM

Existen varios tipos de grandes modelos del lenguaje en uso. Las diferencias entre ellos radican principalmente en cómo están entrenados y cómo se utilizan. He aquí cómo se comparan a simple vista.

## **Zero-shot models (o “Cero disparos”)**

Los modelos de cero disparos (zero-shot)  son modelos generalizados de aprendizaje de lenguaje grande que están entrenados usando un amplio cuerpo de datos para generar respuestas a preguntas. 

Estos modelos generalmente no requieren ningún entrenamiento adicional para su uso. 

Es un enfoque donde un modelo realiza una tarea para la cual no ha recibido ejemplos específicos de entrenamiento

En el contexto de LLMs, se refiere a la capacidad de resolver nuevas tareas simplemente basándose en instrucciones claras proporcionadas en el *prompt*.

## **Fine-tuned or domain-specific models (o “Modelos afinados”)**

- **Definición**: Es un modelo base LLM que ha sido ajustado específicamente para una tarea o dominio concreto. Este ajuste se realiza entrenándolo adicionalmente con datos específicos y configuraciones adaptadas a los objetivos deseados.
- **Ventajas**:
    - Mayor precisión en tareas específicas (e.g., clasificación de texto, generación de respuestas en un dominio).
    - Puede ser más eficiente en términos de recursos si se utiliza en un ámbito estrecho.
- **Ejemplo**: Un modelo GPT entrenado adicionalmente con datos médicos para responder preguntas clínicas.

Cuando un modelo de cero disparos está sujeto a entrenamiento adicional, el resultado final puede ser un modelo afinado. Los modelos afinados (fine-tuned) suelen ser más pequeños que sus contrapartes de cero disparos, ya que están diseñados para manejar problemas más especializados. Codex de OpenAI es un ejemplo de un modelo afinado que es más refinado que su predecesor de modelo de cero disparos, GPT-3, que genera código. Con un dominio específico en finanzas, BloombergGPT es un modelo que realiza tareas financieras.

*Domain-specific and task-specific models are fine-tuned using data specific to the domain they’re built for, such as law, medicine, cybersecurity, art, and countless other fields.*

![image.png](image%2023.png)

**Diferencias entre un modelo fine-tuned y un LLM fundacional:**

- Un modelo fine-tuned está optimizado para una tarea específica, mientras que un LLM funcional es generalista.
- Los datos de entrenamiento y el objetivo definen la capacidad de especialización.

**Un modelo fine-tuned podría considerarse una versión especializada de un LLM funcional, adaptado para maximizar el rendimiento en un contexto determinado**

## **Edge or on-device models (o “Modelos borde”)**

Los modelos de borde pueden funcionar como modelos afinados, pero generalmente tienen un alcance aún más pequeño. Este tipo de modelo a menudo está diseñado para producir comentarios inmediatos basados en la entrada del usuario. Google Translate es un ejemplo de un modelo de borde en acción.

![image.png](image%2024.png)