<h1 align="center">
    Speeches Delivered at the United Nations General Assembly:<break></break>
</h1>
<h2 align="center">
    Pre & Post Cold War Era Sentiment
</h2>


<p align="center">
  <img src="https://live.staticflickr.com/3552/3311542781_71fb3f4618_c.jpg" width="600" height="400">
</p>
# Contents
1. Purpose
2. Data
3. Feature Engineering
4. Predicting Speeches' Era Using Vectorizers
5. Topic Modelling
6. Predicting Speeches' Era Using Topics
7. Visualizing with GemSim

### Purpose
The United Nations General Assembly is the central deliberative, policy-making, and representative organ of the United Nations. The UNGA is responsible for the UN budget, appointing the non-permanent members to the Security Council, appointing the Secretary-General of the United Nations, receiving reports from other parts of the UN system,  making recommendations through resolutions, among other functions it serves. The UNGA is the only UN organ wherein all member states have equal representation. Annual sessions are held under its president or secretary-general in New York City, typically from September through January until all issues are addressed. The first session was in 1946 London, including representatives of the 51 founding nations. [Source: Wikipedia](https://en.wikipedia.org/wiki/United_Nations_General_Assembly)

Speeches are delivered by the representatives from each country at the UNGA's annual session. I sought to model predicitions of speeches given prior to or following the Cold War. The cut-off date is 1992, following the dismantling of the former Soviet Union at the close of 1991. 
I predicted on 7700 speeches if they were given prior to or post the Cold War. I additionally performed topic modelling, predicted speeches' era based on topics as features, and finally 

### Data
Speeches given at the UNGA 1970-2016 are available on [DataWorld](https://data.world/ian/united-nations-general-debate-corpus/).
Distribution of speeches from distinct eras:

### Feature Engineering
After starting out with over 80k features, those features that were included for modelling were only those that had tfidf scores1 above a certain threshold. This process limited the number of features to just over 3k.  
From the Random Forest, feature importances were collected. After removing the features with greatest importance due to concern that the underlying distinctions between the two classes was being overwritten by select dominant features, the models still performed very well.  
Additional stopwords include Namibia, Soviet, Korea, and Cyprus. For a full list of terms added to the stopwords set, see [notes.md](https://github.com/sborodach/capstone_2/blob/main/notes.md)

### Predicting Speeches' Era: Pre & Post Cold War
1. Logistic Regression
    - Fast and simple (few hyperparameters)
    - Hard v Soft classifiers  

|  | Pre-War | Post-War | 
| ----- | ----- | ----- |
| **True** | 729 | 1172 | 
| **False** | 6 | 19 |  

On a first pass, the LR model classified all observations as the dominant class. However, balancing out the classes by removing speeches from the majority class resulted in an effective LR model.  

2. Random Forest Classifier

3. Gradient Boosting Classifier

Evaluation Metrics:
    - _ROC Curve_ + other evaulation metrics  
        
### Topic Modelling
1. Nmf
    - display elbow graph  
    - illustrate progression of increasing n_components  
3. LdA Model: GenSim  
  
### Some Additional Fun Things
    - Predicting based on topics
    - Investigating incorrectly predicted documents  

Further Steps:
    - Feature engineering to improve LR model  

### Thank you
to my instructors Juliana Duncan, Dan Rupp, and Kiara Hearn for their instruction in the Galvanize Data Science Immersive. Thank you additionally to Hailin Du, Alice Tsai, and Noah Shreve for their comments and insight throughout teh formation of this project.

Notes & Lessons Learned:
    - Decision Tree Classifier consistently performed more poorly than the Random Forest and Gradient Boosting models.  
    - Kmeans highlighted a single outlier regardless of the number of a clusters. It turned out to be a document of symbols or encoded text, which I removed from the corpus. Further, k-means clustering resulted in identifying a single outlier that appeared consistently in its own cluster, regardless of the number of clusters. Upon inspection, this document consisted of random symbols and was thus discarded. This is actually a pleasing discovery as the total number of speeches according to the dataset documentation was 7001 and when reading in the various CSV's there were 7002. Thus we then had the correct amount of documents.


20 components
724,   24],
[  13, 1165]]

15 components
[ 725,   23],
[  17, 1161]]
         
10 components
[ 724,   24],
[  18, 1160]

### n_components = 10
|  | Pre-War | Post-War | 
| ----- | ----- | ----- |
| **True** | 724 | 1160 | 
| **False** | 18 | 24 |  

### n_components = 15
|  | Pre-War | Post-War | 
| ----- | ----- | ----- |
| **True** | 725 | 1161 | 
| **False** | 17 | 23 |  

### n_components = 20
|  | Pre-War | Post-War | 
| ----- | ----- | ----- |
| **True** | 724 | 1165 | 
| **False** | 13 | 24 |
