## Data Science Bowl 2019

**Overview:** 
Developed a multi-stack model with threshold optimiser to effectivly predict childhood learning outcomes by utilising data from a game-based learning tool in early childhood education.
<br><br>
This project was based on a Kaggle competition (here) where the goal was to uncover new insights in early childhood education and how media can support learning outcomes. This was also the fifth annual Data Science Bowl (2019), presented by Booz Allen Hamilton and Kaggle.

### 1. Probelm

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

My solution involved using a regression approach to this task where the evaluation was based on the weighted kappa metric. 
Conisdering the ordinal form of the target feature, a regression approach with optimised thresholds were implemented.
<br>
<img src="images/ds-bowl19.png?raw=true"/>

### 3. Results

The resulting model achieved an overall result in the top 7% on the final leaderboard.
