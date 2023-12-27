# MBRNN_GtG1
Creating an ML framework for analyzing G(t)/GI/1 queue.

This repository contains the MBRNN model (MBRNN2.pkl), a Jupyter notebook (main.ipynb) with examples. Also, the file long_sim_180_fix.rar contains labeled data where the number of sequences is 180.

### Instructions:
The input must be in the following structure. The input should be in a PyTorch tensor of (n1,n2,n3). n1 is the number of examples we would like to suggest. 
n2 is the number of sequences for all examples. n3 is the input size per time epoch per example. The first four values are the log values of the service time distribution. It is recommended to scale the mean service time to 1.
The second 4 entries are the log values of the first four moments of the inter-arrival distribution. Then the next 30 entries represent the discrete distribution of the number of customers in the system. n3 must be 38. The values of n1 and n2 can be any integer.

