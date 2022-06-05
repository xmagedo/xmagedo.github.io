##Back door attacks on ML

I have recently worked on project creating AI recognition model and one of the things that interested me is that how would hackers place back door attack on ML model? 
since machine learning is often a blackbox. Back doors can be surprisingly easily set up, but before we jump into the how backdoor can occur in ML, let's have basic idea on 
one shot learning.

### What is one-shot learning? 
One-shot learning can be seen as an approach to train machines in a way that is similar to how humans learn. One-shot learning is an approach to learn a new task using limited supervised data with the help of strong prior knowledge.
In one shot learning, only one image per person is stored in the database, which is passed through the neural network to generate an embedding vector. This embedding vector is compared with the vector generated for the person who has to be recognized. If there exist similarities between the two vectors then the system recognizes that person, else that person is not there in the database. 
This can be understood by the below picture.


 
 
 Basically you want to have access to the training phase or the model 
or to be able to update the model and what you do is train it on a set of data that won't be seen during ordinary execution and you want to train it so that it does what you wanted to do.
As an example, run a neural network that does image recognition using one shot learning, how usually this machine learning program works is that it has a collection of 
users that we have trained on and these will be recognized by the program. When we run the program and use our image to recognize our name or face it will accept that user's face
Now what if a malicious actor add in another user in a way that no one will know. As an example, installing a little backdoor and that's supposed to have root access and the actor manages to infiltrate
this user into these set of users. Now, when we run this program I will be having root user and access to the data. 

