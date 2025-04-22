The problem is:  
  
Estimated time of arrival from current location to destination with the chosen transport, regression  
  
Metrics:   
	time difference between the ETA and actual time.   
  
Questions:  
1. Is this product intended to work everywhere, or in some particular region?  
2. In terms of product requirements, can we assume that we have access to low latency (e.g. compute nodes, key value store)?  
- what is the data are we collecting from the app.   
- what's the size of data  
- What is the computing resources, where is the model based.  
- what is the response time expected?   
- Do we need to explain our model. --> No  
- Data Privacy --> Location data  
- ML security/attack  
- Reliability  
- accuracy  
- Scalability   
- Maintainablitity  
- Adaptablitly.  
  
Concerns:  
- respond time within seconds.   
- Need to update as the location moves.   
  
Summaries of the problem:  
This is a regression problem which updates every minute because there is a change of current traffic and situation.   
  
  
I am going to discuss this system design in a few topics:  
- data engineering  
- feature engineering  
- model develepment and off-line evaluation  
- model deployment and online test  
  
**Think about how this workflow would be**  
  
  
# Data engineering  
We have data such as:  
- location, destination  
- Current traffic： average speed of car, walking, bus,  
- Local weather  
- choice of transport  
- Transport schedule.   
- recent travel time from others.   
- travel route  
labels:  
- existing time from actual travelling  
  
some of these data will be stored in the computing unit and update every 1-5 minutes like traffic, weather, transport schedule, and recent travel time from others.  
  
Some of these would be updated live from user.   
  
## Data sampling  
if we have too much data, we could use reservoir sampling  
[Possible ML system design questions > Whats the tradeoff of reservoir sampling?](../System%20Design/Possible%20ML%20system%20design%20questions.md#Whats%20the%20tradeoff%20of%20reservoir%20sampling?)  
# Feature engineering  
  
  
vectorisation of the data.   
construct route first.   
  
## Model development and off-line evaluation  
Because it is a regression problem.  
- Define a baseline: linear regression,   
Define metrics:  
 - the metric will be the mean absolute error  
propose some models like:  
grid search of SVR, decision tree. XGBoost  
  
![Possible ML system design questions > What's the difference of all models?](../System%20Design/Possible%20ML%20system%20design%20questions.md#What's%20the%20difference%20of%20all%20models?)  
  
  
we will also evaluation the model performance when the number of sample grows.   
  
## Training  
We could also use model ensembles to choose the best vote. (but it is not necessary here)  
  
Considering the training requirement, we could use parallel data training and parallel model training.   
  
- monitor  
- versioning: data version and model version  
  
  
## evaluation  
compare with baseline  
  
error analysis, especially those ones with large difference.   
  
  
## Model deployment  
  
1. cloud based enquery, live inference processing.   
2. batch processing of some constant data. model to process that part and update the features there.   
3. Model optimisation and model compression.   
