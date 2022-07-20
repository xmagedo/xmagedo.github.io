# Phishing detection using ML


 According to recent Cybersecurity reports that the largest contributing factor to more than 16000 cyberattacks were mostly phishing scams which accounted with over 12000 incidents. Often bank customers are hit with phishing frauds emails and SMS and they end victims. A lot of papers out there have gone and used phishing detection using machine learning using random forest. There are different kinds of phishing detection. However, in this blog I will tackle URL phshing detection briefly. 


# URL-Based Features

The first thing to do to tackle and analyse website is URL to find out whether it is a phishing or not. URL phshing domains have distinctive feature in which one  can tell. Below points can tell if it is phishing or not.


### URL length 

### Typosquatted . (google.com → goggle.com)

### If it has a legitimate brand name or not (apple-icloud-login.com)

### Number of subdomains in URL

### Top Level Domain one of the commonly used one?



# Random forest: 

Is classification algorithm which uses bagging and feature randomness when building each individual tree to try to create an uncorrelated forest of trees whose prediction by committee is more accurate than that of any individual tree. It is supervised machine learning Supervised Machine Learning Algorithm that is used widely in Classification and Regression problems. It builds decision trees on different samples and takes their majority vote for classification and average in case of regression. A below image will provide bright idea: 

 

# Phishing detection: 

I found this phishing dataset: https://www.kaggle.com/datasets/shashwatwork/phishing-dataset-for-machine-learning in which I will provide the detection technique using algorithm random forest.


This dataset provide label data which has samples as phish domains and ligit domains. The dataset which will be used in the training phase is a very important point 
to build successful detection mechanism. We have to use samples whose classes are precisely known. So it means, the samples which are labeled as phishing must be 
absolutely detected as phishing. Likewise the samples which are labeled as legitimate must be absolutely detected as legitimate. Otherwise, the system will not work 
correctly if we use samples that we are not sure about. When the journey of the samples is completed, the class that a sample belongs to will become clear.

![image](https://user-images.githubusercontent.com/54819478/179998951-4bd93461-85d8-4e28-adce-65893000a7ce.png)


I begin by downloading the dataset, and then reading it into data frames for convenient examination and manipulation.
 
![image](https://user-images.githubusercontent.com/54819478/179995991-deafa411-e112-4316-a641-1304574d0caf.png)

The dataset consists of several thousand-feature vectors for phishing URLs. There are 30 features, whose names and values are tabulated here:
 

![image](https://user-images.githubusercontent.com/54819478/179996016-2180ba95-84dd-463e-b8ea-ab95bcceab43.png)


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





REF: https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0258361
