## Data Science Bowl 2019

**Overview:** 
Developed a multi-stack model with threshold optimiser to effectivly predict childhood learning outcomes by utilising data from a game-based learning tool in early childhood education.
<br><br>
This project was based on a Kaggle competition (here) where the goal was to uncover new insights in early childhood education and how media can support learning outcomes. This was also the fifth annual Data Science Bowl (2019), presented by Booz Allen Hamilton and Kaggle.

### 1. The Problem

In this challenge, anonymous gameplay data was used, including knowledge of videos watched and games played, 
from the <em>PBS KIDS Measure Up!</em> app, a game-based learning tool developed as a part of the CPB-PBS Ready To Learn Initiative
with funding from the U.S. Department of Education. 
Competitors were challenged to predict scores on in-game assessments and create an algorithm that will lead to better-designed 
games and improved learning outcomes.

The intent of the competition is was to use the gameplay data to forecast how many attempts a child will take to pass a given
assessment (an incorrect answer is counted as an attempt). The outcomes in this competition are grouped into 4 groups 
(labeled  `accuracy_group`  in the data):

3: the assessment was solved on the first attempt<br/>
2: the assessment was solved on the second attempt<br/>
1: the assessment was solved after 3 or more attempts<br/>
0: the assessment was never solved<br/>

<https://www.kaggle.com/c/data-science-bowl-2019>

### 2. Modelling

My solution involved using stacking, an ensemble learning technique, to combine multiple regression models via a meta-regressor (i.e. a linear model). Each prediction is then adjusted to the ordinal form by using a an optimiser and a thresholding technqiue. The predictions of each stack is then considered in a majority voting rule, for evaluation using the weighted kappa metric. 
Conisdering the ordinal form of the target feature, a regression approach with optimised thresholds were implemented.
<br>
<img src="images/ds-bowl19.png?raw=true"/>
In this procedure, the first-level regressors are fit to the same training set that is used prepare the inputs for the second-level regressor, which may lead to overfitting. Therefore, the concept of out-of-fold predictions: the dataset is split into k folds, and in k successive rounds, k-1 folds are used to fit the first level regressor. In each round, the first-level regressors are then applied to the remaining 1 subset that was not used for model fitting in each iteration. The resulting predictions are then stacked and provided -- as input data -- to the second-level regressor. After the training of each StackingCVRegressor, the first-level regressors are fit to the entire dataset for optimal predicitons.
<br>

### 3. Results

The resulting model achieved an overall result in the top 7% on the final leaderboard.
