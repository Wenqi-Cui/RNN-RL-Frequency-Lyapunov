# RNN-Based Reinforcement Learninging Framework for Optimal Frequency Control with Stability Guarantee
This repository contains source code necessary to reproduce the results presented in the following paper:
[Reinforcement Learning for Optimal Frequency Control: A Lyapunov Approach](https://arxiv.org/abs/2009.05654)  

Authors: Wenqi Cui and Baosen Zhang  

University of Washington 


# Motivation
The increase in penetration of inverter-based resources provide us with more  flexibility in frequency regulation of power systems in addition to conventional linear droop controllers. Because of the fast power electronic interfaces, inverter-based resources can be used to realize complex control functions and potentially offer large gains in performance compared to linear controllers. Reinforcement learning has emerged as popular method to find these nonlinear controllers by parameterizing them as neural networks. 

The key challenge with learning based approach is that stability constraints are difficult to enforce on the learned controllers. In addition, the time-coupled dynamics of the power system will 
greatly slow down the training of the neural network. In this paper, we propose to explicitly engineer the structure of neural network based controllers such that they guarantee system stability for all topologies and parameters. This is done by using a Lyapunov function to guide their structures. A recurrent neural network based reinforcement learning architecture is used to efficiently train the weights of controllers. The resulting controllers only use local information and outperform linear droop as well as strategies learned purely by using reinforcement learning. 


# Flexible non-linear controller learnt from the proposed framework
Here we show the action of neural network controller compared with linear droop control
<img src="/Action_Mono.png" height="450px" width="700px" >

# Language and Dependencies
All code are implemented in Python. Data for the power system is imported from MATLAB as 'IEEE_39bus_Kron.mat'. The coeffcient for linear droop control is obtained by fmincon function of Matlab as 'Sol_linear.mat'. We used the open-source Python package Tensorflow 2.0 to implement RNN and train the neural network models.


# Code References
We thank https://sourceforge.net/projects/pg-sync-models for developping open-sorce MATLAB toolbox for Kron Reduction
