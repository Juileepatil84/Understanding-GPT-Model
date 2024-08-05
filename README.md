# Undersatnding-GPT-Models

## Transformer Architecture Overview

The transformer architecture was introduced by researchers at Google’s Brain division in their 2017 paper "Attention Is All You Need." This development revolutionized NLP, leading to the creation of large language models (LLMs) that outperformed previous recurrent neural networks (RNNs). Transformers have excelled in tasks like machine translation, sentiment analysis, question answering, and text summarization, setting new standards and opening up exciting possibilities in AI-driven language tasks.

For a detailed visual explanation, watch this [YouTube video](https://youtu.be/927tHOy-I7U).

## Understanding Transformers in Simple Terms

Before diving into the details, let's use an analogy to understand how transformers work.

Imagine trying to understand a long story. You can't just read it straight through; you need to focus on important parts and ignore less important ones. Transformers work similarly, paying attention to key parts of a sequence while ignoring less relevant parts, even if the important parts are spread out.

### Key Points of the Transformer

1. **Attention Mechanism**: Like focusing on important parts of a story, the transformer pays attention to crucial words in a sentence.
2. **Context Understanding**: It looks at all words in a sentence together, not one by one, to understand how they relate.
3. **Relationship Weighing**: It determines how words are connected, like knowing that "cat" and "mouse" are related.
4. **Combining Insights**: It merges all this knowledge to understand the whole sequence and how words fit together.
5. **Predicting Next Steps**: Based on its understanding, it can predict what words might come next.

## Transformer Architecture Details
![Transformer Architecture](https://github.com/Juileepatil84/Understanding-GPT-Model/blob/main/Transformer%20Architecture.png)

The transformer has two main parts: the encoder and the decoder.

- **Encoder**: Processes the input sequence and creates meaningful representations.
- **Decoder**: Takes these representations and generates the output sequence, like a translation or text continuation.

### Embedding

Before processing text, words must be converted into numerical tokens, known as embeddings.

1. **Word to Vector Conversion**: Each word is represented by a unique numerical vector.
2. **Embedding Layer**: These vectors pass through an embedding layer, associating each word with its corresponding vector.

### Positional Encoding

To provide the model with word order information, positional encodings are added to the embeddings.

1. **Assigning Positions**: Each word gets a unique positional encoding vector representing its position.
2. **Incorporating into Embeddings**: These vectors are added to the word embeddings to include positional information.

### Self-Attention Layer

The self-attention layer captures relationships between words in a sequence.

1. **Queries, Keys, Values**: For each word, create vectors to determine its relevance to other words.
2. **Attention Scores**: Calculate scores indicating how much each word should focus on others.
3. **Weighted Sum**: Combine context from all words for each word using attention scores.
4. **Multiple Attention Heads**: Use multiple sets of queries, keys, and values to focus on different aspects simultaneously.
5. **Generate Output**: Produce contextualized word representations for the feed-forward layer.

### Feed-Forward Layer

The feed-forward layer processes the self-attention layer's output.

1. **Linear Transformation**: Multiply input by a weight and add a bias to project it into a different space.
2. **Activation Function**: Apply a non-linear function, like ReLU, to capture complex patterns.
3. **Second Linear Transformation**: Further adjust the data with a different weight and bias.
4. **Residual Connection & Layer Normalization**: Add the input to the output and normalize to ensure stable training.

### Encoder Process

- **Output to Next Block/Decoder**: If more encoder blocks exist, pass the output to the next one; otherwise, pass it to the decoder.

### Decoder Process

The decoder translates an input sequence into another language or format.

1. **Input Embedding**: Embed the target sequence and add positional encoding.
2. **Masked Multi-Head Self-Attention**: Ensure each position can only attend to previous positions.
3. **Residual Connection & Layer Normalization**: Add output to input and normalize.
4. **Multi-Head Attention over Encoder’s Output**: Focus on relevant parts of the source sequence.
5. **Position-wise Feed-Forward Network**: Apply feed-forward layer to each position.
6. **Output Linear Layer & Softmax**: Map the final output to the target vocabulary and apply softmax to generate probabilities.

In summary, the transformer uses attention mechanisms and feed-forward layers to understand and process sequences, setting new standards in NLP tasks.
