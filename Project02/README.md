# Problem Statement

The dataset has been collected and analysed during a research collaboration of [Worldline and the Machine Learning Group](http://mlg.ulb.ac.be) of ULB (Université Libre de Bruxelles) on big data mining and fraud detection. If you require more details on current and past projects on related topics from the two organizations, please follow these links: [1](http://mlg.ulb.ac.be/BruFence) and [2](http://mlg.ulb.ac.be/ARTML).


The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have `492` frauds out of `284807` transactions. The dataset is highly unbalanced, the positive class (frauds) account for ~ `0.172%` of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues,the original features and background information about the data are not provided. 

- Features `V1`, `V2`, … `V28` are the principal components obtained with PCA.
- The only features which have not been transformed with PCA are `Time` and `Amount`. 
- Feature `Time` contains the seconds elapsed between each transaction and the first transaction in the dataset. 
- The feature `Amount` is the transaction Amount. This feature can be used for example-dependant cost-senstive learning. 
- Feature `Class` is the response variable and it takes value 1 in case of fraud and 0 otherwise.

<br>

(Citation for the project dataset)

_Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi. Calibrating Probability with Undersampling for Unbalanced Classification. In Symposium on Computational Intelligence and Data Mining (CIDM), IEEE, 2015_

<br>

---

___The goal of the project, as set by the instructor is to train an Auto-Encoder on the non-fraudulent transactions, and highlight the difference between them and the fraudulent transactions using the corresponding recreation loss incured by the trained Auto-Encoder___

---

<br>

# 2 Decided scope of model evaluation


___If you are working with the dataset, as it is, without any special approaches,___

- Given the extreme class imbalance ratio of `0.172%`, [3](http://rstudio-pubs-static.s3.amazonaws.com/334864_28050f7860dd4927a596872f0cd52401.html) recommends measuring the accuracy using the Area Under the Precision-Recall Curve (AUPRC) because a confusion matrix will not be meaningful for classification in this context.
- This [Medium article](https://medium.com/datadriveninvestor/rethinking-the-right-metrics-for-fraud-detection-4edfb629c423) recommends using custom loss functions to train machine learning which incorporates the confusion matrix metrics into the loss curve expression.
- This [stats.stackexchange](https://stats.stackexchange.com/questions/222558/classification-evaluation-metrics-for-highly-imbalanced-data) raises the question of choosing the best possible metric for such extremely unbalanced datasets. 


___In my case, where I work with a Fully Connected AutoEncoder,___

- the problem becomes an instance of anomaly detection:
    - the model trains on the "normal" occurences and is trained to produce low recreation errors
    - if the model is fed with an "abnormal" occurence, the recreation error is expected to be higher
- In order to highlight the difference in recreation loss between that of fraudulent transactions from the non-fraudulent ones, I will use superimposed PDF curves for them.

<br>

# My Solution

You may find my notebook rendered by Jupyter nbviewer [here](https://nbviewer.jupyter.org/github/Dexter1618/DeepLearningAcademy/blob/master/Project02/Fraud_Detection.ipynb).
