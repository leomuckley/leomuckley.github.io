## Multi-Input ConvLSTM for Flood Extent Prediction

**Overview:** 
Developed a novel deep learning technique to predict levels of flood extent in East Africa, namely a Multi-Input ConvLSTM. The results of this project demonstrated the effectiveness of this specifc technique to model the spatio-temporal nature of the flooding.
<br><br>
This project was initally my MSc disseratation (here) and was subsequently published at the Machine Learning Advances Environmental Sciences workshop at ICPR 2020 ([paper](/pdf/Flood_Extent_Prediction.pdf), [slides](/pdf/ICPR_Slides.pdf)). 


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
<br>
<img src="images/model.gif?raw=true"/>

### 3. Results

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
