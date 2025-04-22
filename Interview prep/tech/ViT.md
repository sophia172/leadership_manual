[link](https://arxiv.org/abs/2010.11929)  
  
[ViT tradeoff](./ViT%20tradeoff.md)  
  
A Vision Transformer (ViT) is a type of neural network architecture that applies the principles of the Transformer model, originally designed for natural language processing, to image recognition tasks. Here’s an overview of how ViT works:  
  
### 1. Image Patching  
  
Unlike convolutional neural networks (CNNs) that process entire images using convolutional layers, ViT divides an image into fixed-size patches. For example, an image of size 224x224 might be divided into 16x16 patches, resulting in a grid of 14x14 patches.  
  
### 2. Linear Embedding  
  
Each patch is flattened into a 1D vector and then projected into a higher-dimensional space using a linear transformation (a learnable fully connected layer). This step converts each patch into a patch embedding.  
  
### 3. Adding [Positional Encodings](./Positional%20Encodings.md)  
  
Transformers in NLP use [Positional Encodings](./Positional%20Encodings.md) to retain information about the order of words in a sentence. Similarly, in ViT, [Positional Encodings](./Positional%20Encodings.md) are added to the patch embeddings to retain spatial information about the positions of the patches in the image. These encodings are learnable vectors that are added to the patch embeddings.  
  
### 4. Stacking Transformer Encoder Layers  
  
The patch embeddings with [Positional Encodings](./Positional%20Encodings.md) are then fed into a stack of Transformer encoder layers. Each encoder layer consists of:  
  
- **[Multi-Head Self-Attention](./Multi-Head%20Self-Attention.md):** This mechanism allows the model to focus on different parts of the input simultaneously. It computes attention scores between all pairs of patches and generates new representations for each patch based on these scores.  
- **Feed-Forward Neural Network (FFN):** A two-layer MLP with a ReLU activation in between, applied to each patch embedding independently and identically.  
  
Layer normalization and residual connections are applied after each sub-layer (self-attention and FFN).  
  
### 5. Classification Token (CLS Token)  
  
A special learnable token, often referred to as the classification token (CLS token), is prepended to the sequence of patch embeddings. The final hidden state corresponding to this token is used as the aggregate representation of the image for classification tasks.  
  
### 6. Output Layer  
  
The final representation from the CLS token is passed through a fully connected layer (or MLP) to produce the final output, typically a probability distribution over the classes in a classification task.  
  
### Summary of the Workflow  
  
1. **Divide the image** into patches.  
2. **Flatten and linearly embed** each patch.  
3. **Add positional encodings** to the patch embeddings.  
4. **Feed the sequence of embeddings** through Transformer encoder layers.  
5. Use the final hidden state of the **CLS token** for classification.  
  
### Advantages of ViT  
  
- **Scalability:** ViTs can be scaled up with more layers and larger models, benefiting from large-scale training data.  
- **Flexibility:** ViTs can be pre-trained on large datasets and fine-tuned on specific tasks, similar to how BERT and GPT are used in NLP.  
- **Non-local Attention:** The self-attention mechanism allows ViT to capture long-range dependencies and global context more effectively than CNNs.  
  
### Disadvantages and Challenges  
  
- **Data Requirements:** ViTs typically require large amounts of training data to perform well, as they lack the inductive biases inherent in CNNs (like locality and translation invariance).  
- **Computational Cost:** The quadratic complexity of self-attention with respect to the number of patches can make ViTs computationally expensive for high-resolution images.  
  
### Conclusion  
  
ViT represents a significant shift in how image recognition tasks can be approached, leveraging the strengths of Transformer architectures from NLP and adapting them to the domain of computer vision. As with any model, its effectiveness depends on the specific application and dataset, but it has shown state-of-the-art performance on several benchmarks when trained appropriately.