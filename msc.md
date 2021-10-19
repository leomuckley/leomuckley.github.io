## Multi-Input ConvLSTM for Flood Extent Prediction

**Overview:** 
Developed a novel deep learning technique to predict levels of flood extent in East Africa, namely a Multi-Input ConvLSTM. The results of this project demonstrated the effectiveness of this specifc technique to model the spatio-temporal nature of flooding.
<br><br>
This project was initally my MSc dissertation ([link](/pdf/MSc_Dissertation.pdf)), while attending the University of Edinburgh, and my work was presented at the Machine Learning Advances Environmental Sciences workshop at ICPR 2020 ([paper](https://link.springer.com/chapter/10.1007/978-3-030-68780-9_8), [slides](/pdf/ICPR_Slides.pdf)). 

Link to the TensorFlow implementation on [GitHub](https://github.com/leomuckley/malawi-flood-prediction).

### 1. Flood Extent Prediction
Flood  extent  prediction  is  the  task  of  predicting  the  level  of  inundation  for  a specific  location  based  on  a  set  of  flood  conditioning  factors.  In  flood  extent prediction, the goal is to determine where flooding is going to happen and to what  extent. Therefore, the flood extent prediction problem is a task of trying to predict the level of inundation *y* at time *t* based on *m* flood conditiong factors for the previous *k* points in time. 
<br>
<img src="images/ICPR-2c.png?raw=true"/>
<br>
The figure illustrates the modelling process for this problem, where *k* timesteps are considered for each sequence of features, with the goal of predicting the level of inundation (i.e. the fraction of a 1km sq area that is covered in flood water) at a given time *t*.



### 2. Modelling

A novel technique, namely a Multi-Input ConvLSTM, was proposed to effectively model both the temporal and spatial dependencies in the data for the purpose of flood extent prediction. This approach solves some of the issues involving modelling extreme weather events using satellite imagery, such as the ability to model sequential problems using sateliette imagery with varying repetition rates, and thus varying timesteps;  the  ability  to  exploit  local  spatial  dependencies  features in the absence of large training sets, with and without flooding. 
<br><br>
The proposed solution adopts a multi-input architetcture where the model splits the feature set based on how *temporal* a feature is and then propogates the input through the newtork seperately. For instance, highly temporal features, such as precipitation, is propagated through ConvLSTM and LSTM layers and features that are more constant by nature, such as land elevation, are propagated through dense layers.
<br><br>
The following illustration outlines the flow of operations for the Multi-Input ConvLSTM: 
1. First, the subset of features that have a higher repetition rate and are more temporal by nature (e.g. precipitation; soil moisture etc.) are propogated through a combination of ConvLSTM and LSTM layers 
2. Second, the subset of features that have a lower repetition rate and are less temporal by nature (e.g. elevation; distance to river etc.) are propogated through some dense layers
3. The ouptut of these separate networks are then concatenated at a subsequent layer, which is then used in a linear model to output the level of flood extent
<img src="images/model.gif?raw=true"/>

### 3. Evaluation

The data sets used for training and testing were carefully selected to  test  if  the  models  could  generalise  to various flood events. To test this, the following experiments were conducted:
1.  Malawi used for training and testing
2.  Mozambique used for training and Malawi used for testing
3.  Mozambique used for training and Kenya used for testing 
 
First, the models were trained and tested on homogeneous data to better understand the ability  of  the  models  to  perform  on  data  of  a  similar  nature. Second and third,  the  models  were  trained  and  tested  on  heterogeneous  data,  which was  comprised  of  two  different  datasets. Therefore, this would test the ability of the models to generalise well to other flood events. 

#### Homogeneous data
1. Malawi used for both training and testing

Model | RMSE
------------ | -------------
LSTM | 0.0525 +/- 0.0004
LSTM-Autoencoder | 0.0542 +/- 0.01
Multi-Input LSTM | **0.0532 +/- 0.001**
ConvLSTM | 0.0519 +/- 0.0002
Multi-Input ConvLSTM | 0.0572 +/- 0.001
LGBM | 0.1021 +/- 0.0001


#### Heterogeneous data
1. Mozambique used for training and Malawi used for testing
2. Mozambique used for training and Kenya used for testing

Model | Malawi | Kenya
------------ | ------------- | --------------
LSTM | 0.1471 +/- 0.03 | 0.2270 +/- 0.01
LSTM-Autoencoder | 0.1117 +/- 0.02 | 0.2333 +/- 0.01 
Multi-Input LSTM | 0.0803 +/- 0.01 | 0.2120 +/- 0.01
ConvLSTM | **0.1350 +/- 0.02** | **0.2180 +/- 0.01**
Multi-Input ConvLSTM | 0.0890 +/- 0.01 | 0.2169 +/- 0.02
LGBM | 0.2815 +/- 0.002 | 0.2554 +/- 0.01


The results of the experiments show that converting the original flood extent prediction problem into a temporal problem outperforms the current state-of-the-art LGBM model in generalising to various types of flood events. Furthermore, we compare the sub-components of the Multi-Input ConvLSTM model to demonstrate their efficacy separately. These comparisons show that the ConvLSTM architecture is particularly effective at modelling problems where training and test sets have simialr distributions while the Multi-Input architecture was particularly effective when the training and test sets did *not* have similar distributions. 
<br><br>
Furthermore, we see that the Multi-Input ConvLSTM model showed to be effective in both scenarios and thus, demonstrating the ability of the model to generalise to various types of flood events.
