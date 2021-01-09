## Cassava Leaf Disease Classification

**Overview:** 
Developed a method utilising EfficientNet[] model to accurately classify images of Cassava plants to distinguish between healthy and diseased crops. 
<br><br>

### 1. Problem

As the second-largest provider of carbohydrates in Africa, cassava is a key food security crop grown by smallholder farmers because it can withstand harsh conditions. At least 80% of household farms in Sub-Saharan Africa grow this starchy root, but viral diseases are major sources of poor yields. With the help of data science, it may be possible to identify common diseases so they can be treated.

Existing methods of disease detection require farmers to solicit the help of government-funded agricultural experts to visually inspect and diagnose the plants. This suffers from being labor-intensive, low-supply and costly. As an added challenge, effective solutions for farmers must perform well under significant constraints, since African farmers may only have access to mobile-quality cameras with low-bandwidth.

In this competition, we introduce a dataset of 21,367 labeled images collected during a regular survey in Uganda. Most images were crowdsourced from farmers taking photos of their gardens, and annotated by experts at the National Crops Resources Research Institute (NaCRRI) in collaboration with the AI lab at Makerere University, Kampala. This is in a format that most realistically represents what farmers would need to diagnose in real life.

Your task is to classify each cassava image into four disease categories or a fifth category indicating a healthy leaf. With your help, farmers may be able to quickly identify diseased plants, potentially saving their crops before they inflict irreparable damage.

<img src="images/cassava.png?raw=true"/>

### 2. Modelling

Multi-Input ConvLSTMis now proposed to effectively model both the tem-poral and spatial dependencies in the data for the purpose of flood extent predic-tion1. This novel approach solves some of the issues involving modelling extremeweather events using satellite imagery, such as: the ability to model sequentialproblems  with  a  mixture  of  data  types  without  redundant  information  beingincluded  in  the  modelling;  the  ability  to  exploit  local  spatial  dependencies  inthe absence of large high-dimensional training sets. Figure 1 outlines the flow ofoperations for the Multi-Input ConvLSTM. This architecture is also divided intotwo components: (1) for modelling the temporal features, the ConvLSTM model will be utilised; (2) for modelling the constant features a feed-forward network(MLP) will be used. These two components will be combined at a subsequentlayer for before being propagated to the output layer.

<img src="images/model.gif?raw=true"/>

### 3. Results

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
