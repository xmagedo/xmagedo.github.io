## Backdoor attacks on ML

I have recently worked on project creating an AI image recognition model and one of the things that interested me is that how would hackers place backdoor attack on ML 
model? 
Since machine learning is often a black box. Back doors can be surprisingly easily set up, but before we jump into the how backdoor can occur in ML, let's have basic 
idea on one shot learning.

### What is one-shot learning? 

One-shot learning can be seen as an approach to train machines in a way that is similar to how humans learn. One-shot learning is an approach to learn a new task using 
limited supervised data with the help of strong prior knowledge.
In one shot learning, only one image per person is stored in the database, which is passed through the neural network to generate an embedding vector. This embedding 
vector is compared with the vector generated for the person who has to be recognized. If there exist similarities between the two vectors then the system recognizes 
that 
person, else that person is not there in the database. 
This can be understood by the below picture.

![image](https://user-images.githubusercontent.com/54819478/172054208-18969a7a-45e3-4538-a4ae-e3241083e0ab.png)

### Types of one-shot learning

There are various approaches to solve one-shot learning. Roughly speaking, they can be organized into five main categories:

1. Data augmentation methods
2. Model-based methods
3. Metrics-based methods
4. Optimization-based methods
5. Generative modeling-based methods


The following diagram shows the categories of one-shot learning:

![image](https://user-images.githubusercontent.com/54819478/172054674-33c85c8a-e5d0-4eb8-b3ba-005ff98f2cb8.png)
 


Data augmentation is the most commonly used method in the deep learning community to add variations to data, increase data size, and balance data. It's achieved by 
adding some form of noise in the data. For instance, images might be scaled, translated, and rotated; whereas in a natural language processing task, there might be 
synonym replacement, random insertions, and random swaps.
 
### Perofrming backdoor attack on ML

We want to have access to the training phase or the model and be able to update the model, what we do is train it on a set of data that will not be seen during 
ordinary execution, and we want to train it so that it does what we wanted to do. As an example, we run a neural network that does image recognition using one shot 
learning, how usually this machine learning program works is that it has a collection of users that have been trained on and the program will recognize these. When we 
run the program and use our image to recognize our name or face it will accept that user's face. Now what if a malicious actor add in another user in a way that no one 
will know. As an example, installing a little backdoor and that is supposed to have root access and the actor manages to infiltrate this user into these set of users. 
Now, when we run this program we will be having root user and access to the data. 

![image](https://user-images.githubusercontent.com/54819478/172054781-447d69e4-153e-42ca-8aa0-c690902569b4.png)

That is a basic idea on performing backdooor attacks on ML model

Refernce: One-shot Learning with Python Shruti Jadon, Ankush Garg
