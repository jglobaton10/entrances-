# Fake News Classifier 

## Objective 

The objective of this project was to create a classification model  able to  say wether a news report is fake or no.  
  * Test different  machine learning models, Naive Bayes variations and Ensambles) and Depp learnig models (MLP models).

## Data 
For this project it was used a [dataset from kaggle](https://www.kaggle.com/clmentbisaillon/fake-and-real-news-dataset?select=True.csv). The data is composed of two files one for Real news
and one for Fake news, the prior  has 21418 instances, the latest has 23849 instances and both have 4 columns. Each instance represent a news article. 

## Development 
The data went through a several preprocessing steps:
1. Splitting the train and test sets
2. Remove the columns subject and date
3. joint the columns tittle and test 
4. Tokenazation 
5. Remove the noice from text data (removing non ascii characters, punctuation, stopwords, lowercassing and turning numbers into strings)
6. Normalization (steamming and lemmatization)

After the preprocessing step the data was transformed into three different representations:

1. Binary
2. Bag of words
3. Term-frecuency times inverse Document-frecuency

Finally, the  representations were used to train different models:
1. Bernoulli Naive Bayes
2. Categorical Naive Bayes
3. Multinomial Naive Bayes
4. Complement Naive Bayes
5. Random Forest classifier
6. Baggig Classifier
7. Ada Boost classifier
8. MLP with two hidden layers 

## Results

Naive Bayes algorithms 
Using GridSearchCV it was determied that the best model was AdaBoostClasifier with a f1_score of 1 on test.
![image](https://user-images.githubusercontent.com/47225250/124989232-ed46c680-e00c-11eb-8abc-c0bb23accd41.png)

The noteebok with code can be seen in the following [link](https://github.com/jglobaton10/entrances-/blob/main/Fake%20news.ipynb).








 

