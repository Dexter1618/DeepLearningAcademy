# Problem statement discussion

The project is based on the dataset used by Moro et al., 2014 [[1]](http://dx.doi.org/10.1016/j.dss.2014.03.001) in their publication: _S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems_

---

The publication's abstract provides the problem statement for us: " ***...to predict the success of telemarketing calls for selling bank long-term deposits***."

---


The dataset has 20 variables (predictive features) for the target variable `y` which is defined as the answer to the binary question: has the client subscribed a term deposit?
The dataset is based on "Bank Marketing" UCI dataset. [[2]](http://archive.ics.uci.edu/ml/datasets/Bank+Marketing)The data is enriched by the addition of five new social and economic features/attributes (national wide indicators from a ~10M population country, published by the Banco de Portugal and publicly available [[3]](https://www.bportugal.pt/estatisticasweb) online. Please note that the version of the dataset used for the project is not the same as the one used by Moro et.al. 2014. It does not include all attributes due to privacy concerns.
<br>
<br>
The original dataset actually had 150 features with bank client, product and social-economic attributes. A semi-automatic feature selection was explored in the modeling phase, performed with the data prior to July 2012 and that allowed to select a reduced set of 22 features. We are working with this reduced version essentially.
<br>
<br>

The zip file provided by Artem includes two fles:
 - `bank-additional-full.csv` with all examples, ordered by date (from May 2008 to November 2010).
 - `dataset_info.txt` which answers most of the questions relevant to descriptive analysis of the dataset.
 
 ---
***The binary classification goal is to predict if the client will subscribe a bank term deposit***

# My Solution

You may find my notebook rendered by Jupyter nbviewer [here](https://nbviewer.jupyter.org/github/Dexter1618/DeepLearningAcademy/blob/master/Project01/Predictive_Behavior_Modelling.ipynb).
