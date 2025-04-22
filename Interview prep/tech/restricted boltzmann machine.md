A Restricted Boltzmann Machine (RBM) is a type of stochastic neural network used for unsupervised learning. It consists of two layers: a visible layer and a hidden layer, with no connections within each layer but with connections between layers. Here’s a detailed explanation of how RBMs work:  
  
### 1. Architecture  
- **Visible Layer (v):** This layer contains visible units or nodes that represent the input data. Each visible unit corresponds to a feature in the dataset.  
- **Hidden Layer (h):** This layer contains hidden units or nodes that capture dependencies and patterns in the data. The hidden units are not directly observable.  
- **Weights (W):** Each connection between a visible unit and a hidden unit has an associated weight. These weights are learned during training.  
- **Biases:** Each unit in both layers has an associated bias term, $a$ for visible units and $b$ for hidden units.  
  
### 2. Energy Function  
The RBM defines an energy function for the configuration of visible and hidden units:  
$$ E(v, h) = -\sum_i a_i v_i - \sum_j b_j h_j - \sum_{i,j} v_i W_{ij} h_j $$  
where:  
- $v_i$ and $h_j$ are the binary states of visible unit $i$ and hidden unit $j$.  
- $a_i$ and $b_j$ are the biases for visible unit $i$ and hidden unit $j$.  
- $W_{ij}$ is the weight between visible unit $i$ and hidden unit $j$.  
  
### 3. Probability Distribution  
The joint probability distribution over the visible and hidden units is defined in terms of the energy function:  
$P(v, h) = \frac{1}{Z} e^{-E(v, h)}$  
where $ Z $ is the partition function, ensuring the probabilities sum to one:  
$Z = \sum_{v, h} e^{-E(v, h)}$  
  
### 4. Training: Contrastive Divergence  
Training an RBM involves adjusting the weights and biases to minimize the difference between the input data distribution and the distribution represented by the RBM. The most common training algorithm is Contrastive Divergence (CD):  
  
1. **Initialization:** Initialize the weights and biases randomly.  
2. **Positive Phase:**  
   - Given a visible vector $ v $, compute the probabilities of the hidden units being active:  
     $P(h_j = 1 | v) = \sigma(b_j + \sum_i v_i W_{ij})$  
     where $ \sigma $ is the sigmoid function.  
   - Sample the hidden units $ h $ based on these probabilities.  
3. **Negative Phase:**  
   - Reconstruct the visible units $ v' $ using the sampled hidden units:  
   $$   P(v_i = 1 | h) = \sigma(a_i + \sum_j h_j W_{ij}) $$  
   - Compute the probabilities of the hidden units being active given $ v' $:  
      $$P(h_j = 1 | v') = \sigma(b_j + \sum_i v'_i W_{ij})$$  
4. **Weight Update:**  
   - Update the weights and biases using the difference between the data distribution and the model distribution:  
    $$\Delta W_{ij} = \epsilon (\langle v_i h_j \rangle_{data} - \langle v_i h_j \rangle_{recon})$$  
$$     \Delta a_i = \epsilon (\langle v_i \rangle_{data} - \langle v_i \rangle_{recon}) $$  
     $$\Delta b_j = \epsilon (\langle h_j \rangle_{data} - \langle h_j \rangle_{recon}) $$  
     where $\epsilon$ is the learning rate, and  $\langle \cdot \rangle$  denotes expectation over the data or reconstruction.  
  
### 5. Usage  
- **Feature Extraction:** The hidden layer of an RBM can be used to extract features from the data, useful in dimensionality reduction and as a preprocessing step for other machine learning algorithms.  
- **Data Generation:** Once trained, an RBM can generate new data samples by sampling from the learned distribution.  
- **Deep Belief Networks (DBNs):** RBMs can be stacked to form Deep Belief Networks, where the hidden layer of one RBM serves as the visible layer for the next. This hierarchical structure captures increasingly complex patterns.  
  
### Summary  
RBMs are powerful models for unsupervised learning, capturing the underlying patterns in the data by learning the distribution over visible and hidden units. Training involves adjusting weights and biases through contrastive divergence, enabling feature extraction, data generation, and use in deep architectures like DBNs.