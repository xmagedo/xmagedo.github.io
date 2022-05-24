## Machine learning model for penetration testing

In this blog I will be uncovering one how to perform one type of attack on machine learning models called black box in white box adversarial. I will explore two types of attackes 

1. Black box adversarial attack 
2. White box adversarial attack

### Black box attack

Simply put, it alter inputs in machine learning models and results to misclassification. Attackers poison the model in order to change the learning 
outcome, by adding malicious data in the model training phase. This method can be performed, for example, by sending and injecting carefully designed 
samples when data collection is occurring during network operations, to train a network intrusion detection system model.

The below image provides bright idea on adversarial attacks:

![image](https://user-images.githubusercontent.com/54819478/170130629-45aaf2ff-ce35-4dde-998b-e43b55873987.png)

In this image, generaly you are only giving access the internal functions including things such as grading, you are only giving acces to the prediction 
score. some prominent examples of machine learning models that are given to you as black box are google's models online and clarified in the real world. 
This is the most likely scenario a pentration tester will encounter where create a test to get in some service to a machine learning model. 
The goal of adversarial machine learning is to help harden and test for vulnerabilities of the model. 


### White box attack

In white box attack called F GSM which stands for fast gradient signed method, and in this attack and more generally in white box attacks the attacker have 
access to the internal information of the model things such as the architecture gradients and so on. And this allows us to quickly craft and under sail 
instance and interact the model . So whenever we have a neural network and an example you feed in this into the neural network and uses its 
weights to perform some computations such as small applications additions maybe some non linearity using the pixel values of the input.
So the overall error or the overall loss on the input is some RF metric computation involving the weights of the model and the variables which are the 
pixel values. Usually what we do when we are training the neural network is look at this function's loss. Objective key cost is a function only of the 
weights of the model that we think of the input pixels as being fixed which is correct because a single input is just that it's given an image and it
doesn't change. We then compute the gradient of the loss with respect to the weights of the model in an algorithm called back propagation and then we 
perform gradient descent using the grading. So we just go in a direction that will reduce the loss for us but in the adversarial setting we have the exact 
opposite. So our loss which is a function of the model weights and the pixel values instead of having fixed pixel values now fixed model weights and 
the pixel values are what variance. So now what we do is again compute the gradients. But now the gradients are in terms of the pixel values in terms of 
the input. And again all we do is go along the gradient using gradient descent except we are going in the opposite direction because we are looking to 
maximize loss to create larger and larger error as opposed to minimizing it. So that is the basic idea of fast gradient signed method. Find the gradient in 
terms of the pixel values and then perform gradient descent.


The steps are as follows in order to perform any penetration attack on model:

1. Identify a proper adversary's goal
2. Define the adversary's knowledge
3. Formulate the corresponding optimization problem
4. Resample the collected (training and test) data accordingly
5. Evaluate the classifier's security on the resampled data
6. Repeat the evaluation for different levels of adversary knowledge





Reference: https://researchain.net/archives/pdf/Explaining-And-Harnessing-Adversarial-Examples-2127777 

Reference: Mastering Machine Learning for Penetration Testing Chiheb Chebbi

