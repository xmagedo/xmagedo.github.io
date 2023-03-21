# Training Machine Learning Models on Encrypted Data

### Data privacy

When handling senstive infomation, data privacy have beome really important in recent years when handling personal information. However, in this blog post we will explore a technique in which helps in traning data known as secure multi-party computation (SMPC) to train machine learning models on encrypted data without accessing the raw information.

We will explore the below:

1. The Importance of Data Privacy in Machine Learning

2. What is Secure Multi-Party Computation (SMPC)?

3. Getting Started with PySyft

4. Code Example: Training a Neural Network on Encrypted Personal Information

5. Conclusion



### The Importance of Data Privacy in Machine Learning

In general data privacy is in important factor. When traning data in machine learning, often data gets exposed to the machine. However, now there is a technique in which machine learning offers training models on encrypted data allows organizations to build valuable insights while preserving individual privacy.

### What is Secure Multi-Party Computation (SMPC)? 

Secure Multi-Party Computation (SMPC) is a cryptographic technique that allows multiple parties to compute a function on their private inputs without revealing those inputs to each other. SMPC ensures that no single party can access the raw data, providing strong privacy guarantees. This technique is ideal for training machine learning models on encrypted data

### Getting Started with PySyft

For private and secure machine learning 

`pip install syft`

### Code Example: Training a Neural Network on Encrypted Personal Information

So in the below code it provides simple bright idea on how to encrypte personal information during traning and building the model. As we can see we created a domain and two sub-domain. then we send the input data X and target labels y to Alice and Bob. The + operator here is essentially splitting the data into shares, which are distributed to both workers. The data is encrypted using secret sharing, a technique in Secure Multi-Party Computation (SMPC). Then finally we define the neural network architecture using PySyft's SyModule class, which is a wrapper around PyTorch's nn.Module.

# Initialize domain and workers
```
 root = Domain(name="root")
  alice = root.add_subdomain(name="alice")
  bob = root.add_subdomain(name="bob")
  X_enc = X.send(alice) + X.send(bob)
  y_enc = y.send(alice) + y.send(bob)

  class SimpleNN(SyModule):
     def __init__(self, torch_ref):
         super().__init__(torch_ref=torch_ref)
          self.fc1 = self.torch_ref.nn.Linear(3, 10)
          self.fc2 = self.torch_ref.nn.Linear(10, 1)

    def forward(self, x):
        x = self.torch_ref.relu(self.fc1(x))
        x = self.torch_ref.sigmoid(self.fc2(x))
        return x

   model = SimpleNN(torch)
  optimizer = optim.SGD(model.parameters(), lr=0.1)
  ```


### Conclusion 

we have demonstrated how to train a machine learning model on encrypted data using the PySyft library and the secure multi-party computation (SMPC) technique. This approach allows organizations to protect sensitive information while still gaining valuable insights from their data. As privacy concerns grow in importance, techniques like SMPC will become increasingly essential in the development of secure and trustworthy machine learning systems.












REF: https://research.cs.wisc.edu/areas/sec/yao1982-ocr.pdf 

REF: https://www.researchgate.net/publication/239066122_Foundations_of_cryptography_II_Basic_applications


REF: https://github.com/OpenMined/PySyft
