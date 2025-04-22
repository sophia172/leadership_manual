STAR  
  
Thank you for the question. i used few-shot learning to solve the problem.  
i discovered the problem, isolate the problem to a specific cause  
  
  
I recently read about few-shot learning work within meta. i worked on  a similar project.  
  
This project was designed to have a hand gesture recognition model. This model need to be embedded to the hardware which is a pair of hand controller.   
  
During the model development stage, I found out the the accuracy of model is above 90%. I want it to reach 98% to 100%. The errors mainly comes from some of the gestures because the finger movement of these gestures look quite similar. If I decided to increase the complexity of the model, I need to collect more dataset which is time comsuming. A bigger model would also increase the inference latency and add burdens to the Hardware. So i decided to add a error corrector which does a error classification with the limited error data i have, As the system was decomposed into small models. the system is going to be light. Since we have limiated amount of data, very imbalanced label. I was using a combination of few shot learning and blessing of dimensionality.  With this technique,  I managed to used a linear function to achieve high correction result.  This work was published in IJCNN in 2023.   
  
Of course, this work need to be embeded in the FW which is going to be extra work for FW team. In order to utilise their time, I initiated another project which is design a customised gesture recognition model for inividual user, it is similar to the error corrector. Instead of correction. It collects user data and train it on the device. The user detects the   
  
  
  
challenging  
migration as easy as possible  
