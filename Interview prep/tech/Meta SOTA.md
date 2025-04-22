---
tags:
  - SoTA
---
  
- [GAN](./GAN.md)  
- [restricted boltzmann machine](./restricted%20boltzmann%20machine.md)  
# Dataset  
---  
[link](https://paperswithcode.com/datasets)  
- LIAR for fake news dataset  
  
# Storage  
---  
  
## Model storage  
- Google Cloud model registry  
- AWS model registry  
  
## Data storage  
- Google Cloud Storage  
- AWS S3  
  
## Distributed computing  
Apache Spark  
  
# feature engineering for images/videos  
---  
- [Possible ML system design questions > How to process image data](../System%20Design/Possible%20ML%20system%20design%20questions.md#How%20to%20process%20image%20data)  
	- crop   
	- edge detection  
- CNN, autoencoder  
- [ViT](./ViT.md)  
- [DINOv2-Learning Robust Visual Features without Supervision](./DINOv2-Learning%20Robust%20Visual%20Features%20without%20Supervision.md)  
  
- feature fusion  
	- [CLIP is a model from openAI to combine image/text](https://openai.com/index/clip/)  
	- [ImageBind: joint embedding space from many sensors](https://ai.meta.com/blog/imagebind-six-modalities-binding-ai/) by meta  
	- [metaclip is updated version of CLIP from FAIR meta](https://arxiv.org/abs/2309.16671)  
	- [image-text pretraining](./image-text%20pretraining.md) by microsoft (a review)  
- **Bird's eye view generated from two cameras** , used in autonomous driving system  
- **Stereo Depth System** from two cameras  
- AssemblyHands by meta for hand movement.  
  
# Feature engineering for NLPs  
---  
one-hot vector  
n-gram  
word2vec  
GloVe  
Fasttext  
tokeniser from LLM  
  
  
# Similarity search (distance)  
---  
- [spreading vectors](https://arxiv.org/abs/1806.03198)by meta  
  
- [Redis](https://redis.io/docs/latest/develop/get-started/vector-database/)  
- [approximate nearest neighbour](./approximate%20nearest%20neighbour.md)  
- [Faiss](./Faiss.md) by meta  
- [Hierarchical Navigable Small World (HNSW)](./Hierarchical%20Navigable%20Small%20World%20(HNSW).md)  
- [Two-tower network](https://towardsdatascience.com/two-tower-networks-and-negative-sampling-in-recommender-systems-fdc88411601b)  
- [Softmax model](https://developers.google.com/machine-learning/crash-course/multi-class-neural-networks/softmax)  
- [MobileNetV3 search by Google](./MobileNetV3%20search%20by%20Google.md)  
- [Binarised Distance computation suitable for edge device](Binarised%20Distance%20computation%20suitable%20for%20edge%20device.md) by meta  
  
  
# Clustering  
---  
- BIRCH  
- CURE  
- [traditional methods for clustering](./traditional%20methods%20for%20clustering.md)  
  
# Multiclassfication  
---  
  
- [DeiT III - Revenge of the ViT](./DeiT%20III%20-%20Revenge%20of%20the%20ViT.md)  
- [Metrics for multiclassification](https://medium.com/@hatodi0945/a-comparison-between-mse-cross-entropy-and-hinge-loss-4d4fe63cca12)  
- [Traditional methods for multiclassification](./Traditional%20methods%20for%20multiclassification.md)  
  
# Regression  
---  
- Metrics for regression  
- [traditional methods for regression](./traditional%20methods%20for%20regression.md)  
  
# Binary classification  
---  
  
# Deployment  
---  
- [edge in Meta](./edge%20in%20Meta.md)  
- [MobileNetV3 search by Google](./MobileNetV3%20search%20by%20Google.md)  
- [Binarised Distance computation suitable for edge device](Binarised%20Distance%20computation%20suitable%20for%20edge%20device.md)  
- [FEAT - Few-Shot Learning via Embedding Adaptation with Set-to-Set Functions  by Google](./FEAT%20-%20Few-Shot%20Learning%20via%20Embedding%20Adaptation%20with%20Set-to-Set%20Functions%20%20by%20Google.md)  
- [A Practical Stereo Depth System for Smart Glasses](./A%20Practical%20Stereo%20Depth%20System%20for%20Smart%20Glasses.md)  
- [DINOv2-Learning Robust Visual Features without Supervision](./DINOv2-Learning%20Robust%20Visual%20Features%20without%20Supervision.md)  
  
# LLM quantization  
---  
- [GPTQ](./GPTQ.md)  
- [LoRA by Microsoft](./LoRA%20by%20Microsoft.md)   
- [MixKD - towards efficient distillation of LLMs](./MixKD%20-%20towards%20efficient%20distillation%20of%20LLMs.md)  
  
# Generative model  
  
- [Meta's make-a-scene can generate images from sound](https://ai.meta.com/blog/greater-creative-control-for-ai-image-generation/)  
- [Meta's make-a-video can generate videos from text](https://ai.meta.com/blog/generative-ai-text-to-video/)  
  
# Computer vision  
---  
## Segmentation  
  
-  Detectron2  
	- [segment anything](./segment%20anything.md)  
	- [Mask R-CNN](./Mask%20R-CNN.md)  
- PointRend  
- [Weakly supervised few-shot learner](https://scontent-lhr6-1.xx.fbcdn.net/v/t39.8562-6/340930059_764696778582104_277400812224437772_n.pdf?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=TSH3mrovCZ8Q7kNvgFWo19r&_nc_ht=scontent-lhr6-1.xx&oh=00_AYA7hkG2EGJLIcdscpycY5e6MbgP1GrkkkMQhAdUwUOSZw&oe=6668C5FA)  
  
## Stereo  
  
- [A Practical Stereo Depth System for Smart Glasses](./A%20Practical%20Stereo%20Depth%20System%20for%20Smart%20Glasses.md)  
- Stereo disparity estimation