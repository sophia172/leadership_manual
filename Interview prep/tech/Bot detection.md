1. Binary classification   
2. how imbalanced is the data.   
	- Talk about how different imbalance would affect the final result  
	-   
3. Would the size of data matters  
	- small data --> subsample or over sample --> talk about tradeoff  
4. Approach  
	- data-based approach  
	- algorithm-based approach  
	-   
5. Start with a simple base model  
	- A binary decision tree learns to optimally split the feature space with binary decisions. These models are more interpretable since we can directly see the path along the tree that led to the decision. However, they produce a single binary decision that does not allow us to trade off between false positives and negatives.  
	- A logistic regression model learns a linear decision boundary in the feature space and produces a probability distribution over classes, based on the distance from the boundary. Although these models are less interpretable, they allow us to tune a classification threshold for making a binary decision.  
	- Other models include SVMs, neural networks, etc., each with their own pros and cons.  
	-   
6. Talk about evaluation   
	- Recall and precision: Recall is the fraction of actual bots we manage to classify correctly, and precision is the fraction of flagged accounts that were actually bots. A model with high recall and low precision makes many false positive mistakes, whereas a model with high precision but low recall makes many false negative mistakes. One might be more costly than the other, depending on the problem setting.  
	- F1 score: This is the harmonic mean of the precision and recall score and aims to characterize a combination of the two metrics. We can average F1 scores across classes or over the entire dataset.  
	- AUROC: For a model that outputs a distribution, we can vary a threshold to change the recall and precision rates. The plot of the TPR and FPR is called the receiver operating characteristic (ROC) curve, and the area under this curve is the AUROC curve. A value of 0.5 means an essentially random decision and a value of 1.0 means a perfect classifier.  
	- FPR@95: This is the false positive rate achieved when we adjust our decision threshold to classify 95% of the positive classes correctly (95% recall). A low value indicates high precision, even when we require high recall.  
7. Model deployment monitoring  
	- A deployment monitoring system can be generally broken down into two parts: detecting changes in performance and adapting the model.  
		- Detecting changes in performance: Performance is left generally vague here because different metrics may be used to measure different performance indicators. In addition to overall metrics, we should consider metrics on individual groups or regions, metric change over time, and even A/B comparisons of different models. Although some change or degradation is inevitable, large changes due to distribution shift may signal that we need to adjust our model.  
		- Adapting the model: The simplest way to fix a poorly performing model is simply to collect more data and retrain the model. Depending on the model, we may be able to incorporate new information and training data without retraining from scratch. We should make sure to collect the specific data needed to address the shortcomings found through the monitoring systems. This strategy ensures that the model will improve efficiently.  
8. Data distribution shift  
  
  
# [Possible ML system design questions](../System%20Design/Possible%20ML%20system%20design%20questions.md)  
