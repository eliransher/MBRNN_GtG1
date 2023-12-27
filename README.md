# MBRNN_GtG1
Creating an ML framework for analyzing G(t)/GI/1 queue.

This repository contains the MBRNN model (MBRNN2.pkl), a Jupyter notebook (main.ipynb) with examples. Also, the file long_sim_180_fix.rar contains labeled data where the number of sequences is 180.

### Instructions:
The input must be in the following structure. The input should be in a PyTorch tensor of (n1,n2,n3). n1 is the number of examples we would like to infer. 
n2 is the number of sequences for all examples. n3 is the input size per time epoch per example. The first four entries are the log values of the service time distribution. It is recommended to scale the mean service time to 1.
The second 4 entries are the log values of the first four moments of the inter-arrival distribution. Then the next 30 entries represent the discrete distribution of the number of customers in the system. n3 must be 38. The values of n1 and n2 can be any integer.

The function pred_MBRNN (in main.ipynb) is a transient GI/GI/1 queue utility function. One needs to insert four arguments:

* The first four inter-arrival moments (torch tensor of size 4)
* The first four service moments (torch tensor of size 4)
* The initial state distribution (torch tensor of size 4)
* An integer that represents the number of sequences one wishes to infer.

  The output is the distribution of the number of customers in the system as a function of time. The output is a Pytroch tensor size of (1, m1, m2), where m1 is the number of predicted epochs and m2 is the maximum number of customers we compute which is 50. 

