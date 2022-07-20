## According to recent Cybersecurity reports that the largest contributing factor to more than 16000 cyberattacks were mostly phishing scams which accounted with over 12000 incidents. Often bank customers are hit with phishing frauds emails and SMS and they end victims. A lot of papers out there have gone and used phishing detection using machine learning using random forest. I will go over it briefly in this blog. 


Random forest: 

Is classification algorithm which uses bagging and feature randomness when building each individual tree to try to create an uncorrelated forest of trees whose prediction by committee is more accurate than that of any individual tree. It is supervised machine learning Supervised Machine Learning Algorithm that is used widely in Classification and Regression problems. It builds decision trees on different samples and takes their majority vote for classification and average in case of regression. A below image will provide bright idea: 

 

Phishing detection using random forest: 

I found this phishing dataset: https://www.kaggle.com/datasets/shashwatwork/phishing-dataset-for-machine-learning in which I will provide the detection technique using algorithm random forest.

I begin by downloading the dataset, and then reading it into data frames for convenient examination and manipulation.
 

The dataset consists of several thousand-feature vectors for phishing URLs. There are 30 features, whose names and values are tabulated here:
 



we train and test a random forest classifier. The accuracy is pretty high, but depending on how balanced the dataset is, it might be necessary to consider an FP constraint. There are many ways to expand upon such a detector, such as by adding other features and growing the dataset.



from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, confusion_matrix

clf = RandomForestClassifier()
clf.fit(X_train, y_train)
y_test_pred = clf.predict(X_test)
print(accuracy_score(y_test, y_test_pred))
print(confusion_matrix(y_test, y_test_pred))


The following output: 

0.9820846905537459
[[340   7]
 [  4 263]]

