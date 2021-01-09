## Multi-Input ConvLSTM for Flood Extent Prediction

**Overview:** 
Developed a novel deep learning technique to predict levels of flood extent in East Africa, namely a Multi-Input ConvLSTM. The results of this project demonstrated the effectiveness of this specifc technique to model the spatio-temporal nature of the flooding.
<br><br>
This project was initally my MSc dissertation ([link](/pdf/MSc_Dissertation.pdf)) and was subsequently published at the Machine Learning Advances Environmental Sciences workshop at ICPR 2020 ([paper](/pdf/Flood_Extent_Prediction.pdf), [slides](/pdf/ICPR_Slides.pdf)). 


### 1. Flood Extent Prediction
Flood  extent  prediction  is  the  task  of  predicting  the  level  of  inundation  for  a specific  location  based  on  a  set  of  flood  conditioning  factors.  In  flood  extent prediction, the goal is to determine where flooding is going to happen and to what  extent. Therefore, the flood extent prediction problem is a task of trying to predict the level of inundation *y* at time *t* based on some flood conditiong factors for the previous *k* points in time. 
<br>
<img src="images/ICPR-2c.png?raw=true"/>
<br>
The figure illustrates the modelling process for this problem, where *k* timesteps are considered for each sequence of features, with the goal of predicting the level of inundation (i.e. the fraction of a 1km sq area that is covered in flood water) at a given time *t*.



### 2. Modelling

A novel technique, namely a Multi-Input ConvLSTM, was proposed to effectively model both the temporal and spatial dependencies in the data for the purpose of flood extent prediction. This approach solves some of the issues involving modelling extreme weather events using satellite imagery, such as the ability to model sequential problems using sateliette imagery with varying repetition rates, and thus varying timesteps;  the  ability  to  exploit  local  spatial  dependencies  features in the absence of large training sets, with and without flooding. 
<br><br>
The following illustration outlines the flow of operations for the Multi-Input ConvLSTM: 
1. First, the subset of features that have a higher repetition rate and are more temporal by nature (e.g. precipitation; soil moisture etc.) are propogated through a combination of ConvLSTM and LSTM layers 
2. Second, the subset of features that have a lower repetition rate and are less temporal by nature (e.g. elevation; distance to river etc.) are propogated through some dense layers
3. The ouptut of these separate networks are then concatenated at a subsequent layer, which is then used in a linear model to output the level of flood extent
<img src="images/model.gif?raw=true"/>

### 3. Evaluation

The data sets used for training and testing were carefully selected to  test  if  the  models  could  generalise  to various flood events. To test this the following experiments were conducted:
1.  Malawi used for training and testing
2.  Mozambique used for training and Malawi used for testing
3.  Mozambique used for training and Kenya used for testing 
 
First, the models were trained and tested on homogeneous data to better understand the ability  of  the  models  to  perform  on  data  of  a  similar  nature. Second and third,  the  models  were  trained  and  tested  on  heterogeneous  data,  which was  comprised  of  two  different  datasets. Therefore,this would test the ability of the models to generalise well to other flood events. 

The results of the experiments show that converting the original flood extent prediction problem into a temporal problem outperforms the current state-of-the-art LGBM model in generalising to various types of flood events. Furthermore, we compare the sub-components of the Multi-Input ConvLSTM model to demonstrate their efficacy separately. These comparisons show that the ConvLSTM is particularly effective at when the training and test sets are similar while the Multi-Input architecture was particularly effective when the training and test sets. Furthermore, the Multi-Input ConvLSTM model showed to be effective in either scenario and for the various types of floods.
