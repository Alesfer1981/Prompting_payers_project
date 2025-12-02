---
title: Clasificación de los LLM
nav_order: 6
parent: LLM – Modelos de Lenguaje
---

# Clasificación de los LLM

Los **LLMs (Large Language Models)** se pueden clasificar según diferentes criterios, como el propósito, la arquitectura, y los datos con los que fueron entrenados. Aquí tienes una visión general de los principales tipos:

---

## **1. Según su Arquitectura**

- **Modelos Basados en Transformers**:
    - Son los más comunes y avanzados. Utilizan la arquitectura Transformer, que permite procesar texto en paralelo y entender relaciones contextuales a largo plazo.
    - Ejemplos: GPT (OpenAI), BERT (Google), LLaMA (Meta).
- **Modelos Basados en RNNs o LSTMs** *(menos comunes hoy en día)*:
    - Eran populares antes de los Transformers, pero tienen limitaciones para procesar secuencias largas.
    - Ejemplo: seq2seq con atención.

---

## **2. Según su Propósito Principal**

- **Modelos Generativos**:
    - Se centran en generar texto coherente y creativo.
    - Ejemplo: GPT-4, GPT-3, BLOOM.
- **Modelos de Comprensión**:
    - Diseñados para analizar y entender texto, en lugar de generarlo.
    - Ejemplo: BERT, RoBERTa, DistilBERT.
- **Modelos Mixtos (Generación y Comprensión)**:
    - Pueden generar y entender texto con igual eficacia.
    - Ejemplo: T5 (Text-to-Text Transfer Transformer), FLAN-T5.

---

## **3. Según el Tamaño y Alcance**

- **Modelos Generales**:
    - Entrenados con una amplia variedad de datos y capaces de manejar muchas tareas.
    - Ejemplo: GPT-4, ChatGPT, Claude (Anthropic).
- **Modelos Especializados**:
    - Entrenados o afinados para tareas específicas, como redacción médica, programación, o derecho.
    - Ejemplo: BioGPT (biomedicina), Codex (programación).

---

## **4. Según el Idioma o Contexto**

- **Modelos Multilingües**:
    - Pueden manejar múltiples idiomas en una sola arquitectura.
    - Ejemplo: mBERT, XLM-R.
- **Modelos Monolingües o de Idioma Específico**:
    - Diseñados para un solo idioma, como modelos específicos para español, chino o francés.
    - Ejemplo: BETO (para español).

---

## **5. Según su Acceso y Licencia**

- **Modelos Abiertos**:
    - Están disponibles para que cualquiera los use, ajuste o investigue.
    - Ejemplo: GPT-NeoX, BLOOM, LLaMA.
- **Modelos Privados o Comerciales**:
    - Son propiedad de una empresa y suelen ser de pago.
    - Ejemplo: GPT-4 (OpenAI), Claude (Anthropic).

---

## **6. Según su Entrenamiento**

- **Modelos Preentrenados (Pre-trained Models)**:
    - Entrenados con grandes cantidades de datos y luego afinados para tareas específicas.
    - Ejemplo: GPT-3, BERT.
- **Modelos Ajustados (Fine-Tuned Models)**:
    - Basados en un modelo preentrenado, pero adaptados a un dominio específico o tarea.
    - Ejemplo: Codex (GPT afinado para programación).

---