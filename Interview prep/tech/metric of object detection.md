  
# Intersection-over-Union  
- **True Positives [TP]**  
  
Number of detections with IoU>0.5  
  
- **False Positives [FP]**  
  
Number of detections with IoU<=0.5 or detected more than once  
  
- **False Negatives [FN]**  
  
Number of objects that not detected or detected with IoU<=0.5  
  
- **Precision**  
  
Precision measures how accurate your predictions are. i.e. the percentage of your predictions that are correct.  
  
Precision = True positive / (True positive + False positive)  
  
- **Recall**  
  
Recall measures how good you find all the positives.   
  
Recall = True positive / (True positive + False negative)  
![Pasted image 20240524150202.png](../Pasted%20image%2020240524150202.png)  
  
  
- **AP**  
  
The general definition for the Average Precision(AP) is finding the area under the precision-recall curve.  
  
- **mAP**  
  
The mAP for object detection is the average of the AP calculated for all the classes. mAP@0.5 means that it is the mAP calculated at IOU threshold 0.5.