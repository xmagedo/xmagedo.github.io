## Penetration testing for machine learning model

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

In white box attack called FGSM which stands for fast gradient signed method, this attack and more generally in white box attacks the attacker have 
access to the internal information of the model such as the architecture gradients. And this allows us to interact with the model. So whenever we 
have a neural network and we feed that neural network and use its weights to perform some computations such as small applications additions or maybe some non linearity 
using the pixel values of the input. So the overall error or the overall loss on the input is some metric computation involving the weights 
of the model and the variables which are the pixel values. Usually what we do when we are training the neural network is to look at the loss function. We then compute 
the gradient of the loss with respect to the weights of the model in an algorithm called back propagation and then we perform gradient descent using the grading. So 
we go in a direction that will reduce the loss for us but in the adversarial setting we have the exact opposite. So our loss which is a function of the model, the 
weights and the pixel values instead of having fixed pixel values now fixed model weights and the pixel values are what variance. So now what we do is again compute 
the gradients. But now the gradients are in terms of the pixel values in terms of the input, and again all we do is go along the gradient using gradient descent except 
we are going in the opposite direction because we are looking to maximize loss to create larger and larger error as opposed to minimizing it. So that is the basic idea 
of fast gradient signed method. Find the gradient in terms of the pixel values and then perform gradient descent.


### Steps to perform penetration attack on ML model


The steps are as follows in order to perform any penetration attack on model:

1. Identify a proper adversary's goal
2. Define the adversary's knowledge
3. Formulate the corresponding optimization problem
4. Resample the collected (training and test) data accordingly
5. Evaluate the classifier's security on the resampled data
6. Repeat the evaluation for different levels of adversary knowledge


As an example: 

Information security professionals are doing their best to come up with novel techniques to detect malware and malicious software. One of the trending techniques is 
using the power of machine learning algorithms to detect malware. On the other hand, attackers and cyber criminals are also coming up with new approaches to bypass 
next-generation systems. In a demonstration done by the Search And RetrieVAl of Malware (SARVAM) research unit, at the Vision Research Lab, UCSB, the researchers 
illustrated that, by changing a few bytes, a model can classify a malware as a goodware. This technique can be performed by attackers to bypass malware classifiers, 
through changing a few bytes and pixels. In the demonstration, the researchers used a variant of the NETSTAT program, which is a command-line network utility tool that 
displays network connections. In the following image, the left-hand side is a representation of the NETSTAT.EXE malware, and the second is detected as a goodware. As 
you can see, the difference between the two programs is unnoticeable (88 bytes out of 36,864 bytes: 0.78%), after converting the two types of files into grayscale 
images and checking the differences between the two of them:

![image](https://user-images.githubusercontent.com/54819478/170436079-cc0ad689-3c79-4dcd-a5d6-4d2c117a8ee7.png)


Neural networks can be tricked by adversarial samples. Adversarial samples are used as inputs to the neural network, to influence the learning outcome. A pioneering 
research project, called Explaining and Harnessing Adversarial Networks, conducted by Ian J. Goodfellow, Jonathon Shlens, and Christian Szegedy (at Google), showed 
that a small amount of carefully constructed noise can fool the neural network into thinking that the entered image is an image of a gibbon and not a panda, with 99.3% 
confidence. The neural network originally thought that the provided image was a panda, with 57.7% confidence, which is true; but it is not the case in the second 
example, after fooling the network





Reference: https://researchain.net/archives/pdf/Explaining-And-Harnessing-Adversarial-Examples-2127777 

Reference: Mastering Machine Learning for Penetration Testing Chiheb Chebbi

