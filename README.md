# SelfAttention

Self-attention, also known as intra-attention or internal attention, is a mechanism used in artificial neural networks, particularly in deep learning models such as transformers. It allows the model to weigh the importance of different elements in a sequence (e.g., words in a sentence, pixels in an image) by considering the relationships between all pairs of elements in the sequence.

In the context of natural language processing (NLP), self-attention has been instrumental in tasks such as machine translation, text summarization, and language understanding. It enables the model to capture contextual information efficiently, as each element in the sequence can attend to all other elements, learning which parts of the input are most relevant to each other.

Here's a simplified explanation of how self-attention works within a transformer model:

Input Embeddings: The input sequence (e.g., a sentence) is first transformed into embeddings, which represent each element (e.g., word) in a continuous vector space.
Query, Key, and Value: These embeddings are then linearly transformed into three sets of vectors: Query, Key, and Value vectors. These transformations are learned during the training process.
Similarity Scores: For each element in the sequence, the model calculates a similarity score with respect to every other element. This is done by computing the dot product between the Query vectors of the current element and the Key vectors of all other elements. These similarity scores represent how much attention each element should pay to the others.
Attention Weights: The similarity scores are then scaled and passed through a softmax function to obtain attention weights, ensuring that the weights sum up to 1 across all elements. These attention weights determine how much each element should contribute to the representation of the current element.
Weighted Sum: The weighted sum of the Value vectors, where the weights are given by the attention weights, yields the final representation for each element. This process is repeated for all elements in the sequence.
By allowing each element to attend to others in the sequence and adaptively weight their contributions, self-attention enables the model to capture complex relationships and dependencies within the input data, leading to state-of-the-art performance in various NLP tasks.

### Example 1: 
In this example:

input_sequence represents a sequence of token embeddings. Each row corresponds to the embedding of a token in the sequence.
We define learnable weight matrices W_q, W_k, and W_v to transform the input embeddings into Query, Key, and Value vectors, respectively.
d_k represents the dimensionality of Query and Key vectors.
The self_attention function calculates attention scores by taking the dot product of Query and Key matrices, applies softmax to obtain attention weights, and then computes the weighted sum of Value vectors.
Finally, we apply the self_attention function to the input_sequence and print the output.
This example demonstrates the basic steps of self-attention, but in practice, real-world implementations involve additional complexities such as multi-head attention and layer normalization, among others.

### Example 2:
We use NLTK for tokenizing the input sentence into words.
We utilize pre-trained GloVe embeddings (you can replace it with other embeddings as per your choice).
The sentence_to_embeddings function converts each word in the sentence into its corresponding embedding. If a word is not found in the GloVe vocabulary, it uses a zero vector.
We then apply self-attention using the self_attention function as defined in the previous example.
Finally, we print the output after self-attention.
