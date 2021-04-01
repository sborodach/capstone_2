<p align="center">
    Speeches of the United Nations General Assembly:
    Predicting Pre/Post Cold War Era & Speech Topics
</p>

### Purpose
The United Nations General Assembly is the central deliberative, policy-making, and representative organ of the United Nations. The UNGA is responsible for the UN budget, appointing the non-permanent members to the Security Council, appointing the Secretary-General of the United Nations, receiving reports from other parts of the UN system,  making recommendations through resolutions, among other functions it serves. The UNGA is the only UN organ wherein all member states have equal representation. Annual sessions are held under its president or secretary-general in New York City, typically from September through January until all issues are addressed. The first session was in 1946 London, including representatives of the 51 founding nations. [Source: Wikipedia](https://en.wikipedia.org/wiki/United_Nations_General_Assembly)

Speeches are delivered by the representatives from each country at the UNGA's annual session. I sought to model predicitions of speeches given prior to or following the Cold War. The cut-off date is 1992, following the dismantling of the former Soviet Union at the close of 1991.

### Data
Speeches given at the UNGA 1970-2016 are available on [DataWorld](https://data.world/ian/united-nations-general-debate-corpus/).

Distribution of speeches from distinct eras: 

### Word Counts v TFIDF
_What is TFIDF?_
TFIDF is a score of each and every word in the corpus across all documents. It is tf * idf, or tf(term,document) * idf(term,corpus). The **Term Frequency (TF)** of a word in a document, simlpy a raw count of instances a word appears in a document. The **Inverse Document Frequency (IDF)** of a word across the set of documents. This means, how common or rare a word is in the entire document set. The closer it is to 0, the more common a word is. This metric is calculated by taking logarithm of the total number of documents divided by the number of documents that contain a word. So, if the word is very common and appears in many documents, this number will approach 0. Otherwise, it will approach 1.  
SciKitLearn functions include both a WordCount Vectorizer and a TFIDF Vectorizer. The former is useful for displaying the distribution of words. However, when predicting on natural language, generating TFIDF values for the vectors provides relevance of words across documents, contextualizing them in terms of appearance in a given document, as well as across all documents in the corpus as whole. 

### Feature Engineering
After starting out with over 80k features, those features that were included for modelling were only those that had tfidf scores1 above a certain threshold. This process limited the number of features to just over 3k.  
Further, k-means clustering resulted in identifying a single outlier that appeared consistently in its own cluster, regardless of the number of clusters. Upon inspection, this document consisted of random symbols and was thus discarded. This is actually a pleasing discovery as the total number of speeches according to the dataset documentation was 7001 and when reading in the various CSV's there were 7002. Thus we then had the correct amount of documents.  
From the Random Forest, feature importances were collected. After removing the features with greatest importance due to concern that the underlying distinctions between the two classes was being overwritten by select dominant features, the models still performed very well.  
    - **Namibia**  
    - **Kampuchea**  
    - **apartheid**   
    - **Soviet** Dissolution of the Soviet Union at the end of 1991  
    - **Boutros Ghali** was the secratary general of the UN from 1992-1996  
    - **Bosnia & Herzegovnia** decalared independence in 1992  
    - **thirty** refers to session numbers (thirty-eight, thirty-nine) strong influencer for classification of pre-war era  
    - **Korea**  
    - **Vietnam**  
    - **Guido de Marco** Guido de Marco President of the UN General Assembly in 1990  
    - **Javier Pérez de Cuéllar** was the Secratary General of the UN from '82-'91  
    - **detente** Most often, the term is used for a phase of the Cold War. It was the policy of relaxing tensions between the Soviet Union and the West, as promoted by Richard Nixon, Henry Kissinger and Leonid Brezhnev, between 1969 and 1974.  
    - **Cyprus**  
    - **Waldheim** Kurt Waldheim, Secratary General of the UN from '72-'81  
    - **425, 435, & 1978** Security Council Resolution 425 and Resoltuion 435 both in 1978  
    - **Somalia**
    - **millennium**

### Model Performance
1. Logistic Regression
    - Fast and simple (few hyperparameters)
    - Hard v Soft classifiers  

|  | Post-War | Pre-War | 
| ----- | ----- | ----- |
| **Imbalanced Classes** | | |
| **True** | 1138 | 0 |
| **False** | 788 | 0 |
| **Balanced Classes** | | |
| **Correct** | 722 | 740 | 
| **Incorrect** | 7 | 53 | 
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

Notes & Lessons Learned:
    - Decision Tree Classifier consistently performed more poorly than the Random Forest and Gradient Boosting models.  
    - Kmeans highlighted a single outlier regardless of the number of a clusters. It turned out to be a document of symbols or encoded text, which I removed from the corpus.
