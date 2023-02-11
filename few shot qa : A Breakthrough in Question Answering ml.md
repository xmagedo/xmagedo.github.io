
# Few shot QA 


I was working on cs224u natural language process. I was happy to learn new tool and skills on how few shot QA works. 
First I will start by giving bright idea on few shot QA. It stands Question Answering (QA) has been a critical task in the field of Natural Language Processing (NLP) for many years. The goal of QA is to develop algorithms that can understand and answer questions accurately and efficiently. However, most traditional QA models require large amounts of training data to perform well, which can be a challenge in domains where annotated data is scarce.

Enter Few-shot Question Answering (QA), a new approach that allows QA models to learn from a small amount of training data. In this blog post, we will explore a new approach to few-shot QA that combines the power of ColBERT, a state-of-the-art pre-trained language model, with a retrieval-based approach to answer questions.

As an example: 

For example,

Question: What did Albert Einstein win the Nobel Prize for?
Answer: The law of the photoelectric effect.

1. A model has the capability to recall and provide an accurate answer to a question that was presented during training.
2. A model has the ability to respond to new questions during evaluation by selecting an answer from the ones it encountered during training.
3. A model can answer unique questions even if their answers are not found in the training data.


![image](https://user-images.githubusercontent.com/54819478/218279043-a4aa95ba-830e-4a80-8a8a-48c7ab178759.png)




# ColBERT for QA
ColBERT is a pre-trained language model developed by OpenAI. It is based on the transformer architecture and has been fine-tuned on a large corpus of text data to perform various NLP tasks, including QA. The ColBERT model has been shown to outperform many other pre-trained models in terms of accuracy and efficiency, making it an ideal choice for few-shot QA.

ColBERT is a pre-trained language model developed by OpenAI. It is based on the transformer architecture and has been fine-tuned on a large corpus of text data to perform various NLP tasks, including QA. The ColBERT model has been shown to outperform many other pre-trained models in terms of accuracy and efficiency, making it an ideal choice for few-shot QA.


# cs224u task

In this course I used EleutherAI. It is based on the transformer architecture and has been fine-tuned on a large corpus of text data to perform various NLP tasks, including QA and I used SQUAD datasets to build the model. In the homework, it offers few questions. 

First, to build Few-shot OpenQA with no context, with no context refers to a task in natural language processing where a model is trained to answer questions using a small number of examples, without considering the surrounding context. In this type of QA, the model is not given any additional information other than the question and the answer, and it must rely on its pre-trained knowledge to answer the questions.

The goal of few-shot OpenQA with no context is to develop models that can generalize their knowledge to new questions, even when only a small number of training examples are available. This is particularly important for scenarios where annotated data is scarce or costly to obtain.

Second task, to build Few-shot OpenQA. The goal of few-shot OpenQA is to build models that can generalize their knowledge and answer new questions accurately, even when only a limited amount of training data is available.

Traditional OpenQA models are trained on large datasets of questions and answers, and typically use the surrounding context to help answer questions. In contrast, few-shot OpenQA reduces the amount of training data required and simplifies the task by focusing on answering questions based solely on the question and answer pair. 

Third, building answer scoring in which 𝑃(passage∣question) is defined only for the top 𝑘 passages and defined by the softmax of the top 𝑘 scores returned by the retriever. 

Fourth, building the original system in which you will be presented with multiple choices to build your model that along with answer scoring

Finally, the bake off. The purpose of a bakeoff is to compare and evaluate different models or algorithms in a fair and systematic manner, and to identify the best models or approaches for a specific task. Bakeoffs are often organized and conducted by research institutions or academic organizations, and the results are often published in academic papers or presented at conferences.

Below is the screen shot of my bake off result. It may require a bit of tunning :) 


![EC4686CF-C6F6-4082-B049-413596E13780_1_105_c](https://user-images.githubusercontent.com/54819478/218279709-023fbad9-b8fa-4e7f-98b8-fe1d43c842a7.jpeg)





