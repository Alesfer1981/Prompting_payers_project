# Tokenización (Tokenization)

- Un **token** no siempre es una palabra completa.
    
    Puede ser:
    
    - una palabra entera (ej. *dog*),
    - parte de una palabra (ej. *com* + *puter*),
    - o incluso un símbolo (*?*, *#*, etc.).

Esto depende de cómo se haga la **tokenización**. Por eso los LLM no trabajan directamente con “palabras”, sino con estas unidades mínimas llamadas tokens.

# **What is tokenization?**

Tokenization is the first step and the last step of text processing and modeling. Texts need to be represented as numbers in our models so that our model can understand. Tokenization breaks down text into tokens, and each token is assigned a numerical representation, or index, which can be used to feed into a model. In a typical LLM workflow:

- We first encode the input text into tokens using a tokenizer. Each unique token is assigned a specific index number in the tokenizer’s vocabulary.
- Once the text is tokenized, these tokens are passed through the model, which typically includes an embedding layer and transformer blocks. The embedding layer converts the tokens into dense vectors that capture semantic meanings. Check out our [embedding guide](https://docs.mistral.ai/capabilities/embeddings/overview/) for details. The transformer blocks then process these embedding vectors to understand the context and generate results.
- The last step is decoding, which detokenize output tokens back to human-readable text. This is done by mapping the tokens back to their corresponding words using the tokenizer’s vocabulary.

Tokenization is the first step in transforming raw text into a format that machine learning models can understand. Today, we’ll explore how to implement tokenizers in Python using the Hugging Face library.

📖 What you’ll learn today:

🔹 Loading Pre-trained Tokenizers – Leverage (aprovechar) powerful models like bert-base-uncased.

🔹 Tokenizing Text – Converting raw text into token IDs, attention masks, and more.

🔹 Passing Tokens to Models – Using tokenized inputs to extract meaningful embeddings.

🔹 Model Outputs – Understanding last_hidden_state and pooler_output.

By the end of today's lesson, you'll be able to implement tokenizers effortlessly and prepare your text data for advanced NLP tasks.

![image.png](assets/images/image%2018.png)

To prepare language inputs for transformers, we convert an input sequence into tokens and then into input embeddings. At a high level, an input embedding is a high-dimensional vector that represents the meaning of each token in the sentence. This embedding is then fed into the transformer for processing

![image.png](assets/images/image%2019.png)
