[link](https://openaccess.thecvf.com/content_CVPR_2020/papers/Ye_Few-Shot_Learning_via_Embedding_Adaptation_With_Set-to-Set_Functions_CVPR_2020_paper.pdf)  
  
---  
  
This paper presented a novel method for yielding embeddings so the instances are discriminative and task-specific. It deals with **UNSEEN/NEW** labels  
  
When new instances comes into the system, **FEAT** pushes new instances with new labels away from existing clusters. This is the adaptation procedure.  
  
we propose to adapt those embeddings for each target task with a set-to-set function  
  
The function set $f(\cdot)$ contains both embedding function and classifier. Once we have the new data, we only updates the embedding function instead of classifier. 