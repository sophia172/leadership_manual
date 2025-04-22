  
similarity can be measured in   
  
Cosine  
dot product  
euclidean distance.   
  
  
# Content-based filtering  
  
Uses _similarity between items_ to recommend items similar to what the user likes.  
  
similarity matrix is the dot product of user embedding and item embedding  
  
**Pro**  
- Does not any data about other users.   
- can capture specific interests and niche items   
**Con**  
- Requires a lot of domain knowledge, we need to know the embedding of the posts  
- Can only make recommendation based on existing interestes.  
  
# Collaborative filter  
  
Uses _similarities between users and items simultaneously_ to provide recommendations.  
recommend based on   
- similairy to movies the user has liked in the past  
- Movies that similar users liked  
  
feedback matrix is prduct between user embedding and item embedding  
we can use matrix factorisation to learn user embedding and item embeddings  
  
**cons** :   
- Cannot handle fresh items  
- hard to include side features for query/item  
**Pro**:  
- do not need domain knowledge  
- can help user discover new interests  
- does not need contextural features, can be used as one of multiple candidate generators.  
-   
  
# process  
- measuring similarities  
- cluster users