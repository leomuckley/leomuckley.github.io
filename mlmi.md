## Multi-Input ConvLSTM for Flood Extent Prediction

**Overview:** 
Developed a novel deep learning technique to predict levels of flood extent in East Africa, namely a Multi-Input ConvLSTM. The results of this project demonstarted the effectiveness of this specifc technique to model the spatio-temporal nature of the flood conditioning factors.
<br><br>
This project was initally my MSc disseratation (here) and was subsequently published at the Machine Learning Advances Environmental Sciences workshop at ICPR 2020 (paper,presetation, slides). 

### 1. Flood Extent Prediction

The prediction of flood extent and location is a task of trying to predict the level of inundation $y$, where $0 \le y \le 1$, at time $t$ based on $M$ features for the previous $k$ points in time. In this problem, the level of inundation is the fraction (i.e. value in of a 1km sq polygon that is covered in flood water at time $t$ and each feature $m$, is a sequence of $k$ timesteps (e.g. daily total precipitation). It is these $M$ sequences that are to be utilised to predict flood extent. This study will focus on investigating various deep learning techniques to determine the best method of combining these sequences. 

Figure 1.1 demonstrates the modelling process for this problem, where $k-1$ timesteps are considered for each sequence of features. For example, one measurement could be the total precipitation level of a location at timestep $t-k$ with the final timestep at $t-1$. This example would then predict the flo

<img src="images/ICPR-2c.png?raw=true"/>

### 2. Modelling

Multi-Input ConvLSTMis now proposed to effectively model both the tem-poral and spatial dependencies in the data for the purpose of flood extent predic-tion1. This novel approach solves some of the issues involving modelling extremeweather events using satellite imagery, such as: the ability to model sequentialproblems  with  a  mixture  of  data  types  without  redundant  information  beingincluded  in  the  modelling;  the  ability  to  exploit  local  spatial  dependencies  inthe absence of large high-dimensional training sets. Figure 1 outlines the flow ofoperations for the Multi-Input ConvLSTM. This architecture is also divided intotwo components: (1) for modelling the temporal features, the ConvLSTM model will be utilised; (2) for modelling the constant features a feed-forward network(MLP) will be used. These two components will be combined at a subsequentlayer for before being propagated to the output layer.

<img src="images/model.gif?raw=true"/>

### 3. Results

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
