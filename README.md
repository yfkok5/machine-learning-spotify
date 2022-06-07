# Machine Learning DJ
## 1. Introduction
This respository applies machine learning to data from the Spotify API. The data includes a number of playlists which were compiled based on 3 distinct genres, which are:
* Jazz
* House
* RnB

We also have data which is a list of Ryan's top 20 favourite songs, to which we applied NLP and Sentiment Analysis. 

The results are outlined below.

See instructions for how to use this repsitory at the end of the README.

## 2. NLP
### a. Sentiment Analysis
We completed a sentiment analysis on 20 of Ryan's favourite songs. The sentiment analysis was for both song titles and song lyrics.

The mean sentiment for titles was neutral (89.1%). This was also the case for song lyrics (71.6%).

![Alt_text](/sentiment_table.png)

### b. NLP

The top 10 words for Ryan's favourite song titles were as follows:

1. 'afire'
2. 'angels'
3. 'mama'
4. 'acoustic'
5. 'poet'
6. 'pendulum'
7. 'love'
8. 'given'
9. 'us'
10. 'take'

The top 10 words for Ryan's favourite song lyrics were as follows:

1. 'la'
2. 'oh'
3. 'im'
4. 'like'
5. 'love'
6. 'one'
7. 'na'
8. 'back'
9. 'wa'
10. 'dont'

The top 10 four-word phrases from the lyrics of Ryan's favourite songs were as follows:

1. 'wan', 'na', 'wake', 'one'
2. 'na', 'wake', 'one', 'day'
3. 'mama', 'mama', 'heywe', 'aint'
4. 'mama', 'heywe', 'aint', 'coming'
5. 'heywe', 'aint', 'coming', 'home'
6. 'mama', 'dont', 'stress', 'mindwe'
7. 'dont', 'stress', 'mindwe', 'aint'
8. 'stress', 'mindwe', 'aint', 'coming'
9. 'mindwe', 'aint', 'coming', 'home'
10. 'mama', 'gon', 'na', 'alrightdry'

### c. Word Cloud

See a Word Cloud based off the lyrics of Ryan's top 20 favourite songs below:

![Alt_text](/ryanlyrics_wordcloud.png)

## 3. Machine Learning

### a. Neural Network Model
This is a demonstration of how we utilise Neural Network in Machine learning to make genre predictions for the 1,085 songs that we have on spotify. This playlist only consist of 3 genres (which will serve as our "target"):

1) R&B
2) Jazz
3) Rock

### b. Data Analytics
We ran a feature importance analysis and figured that these 3 audio features played a big role in our machine learning model predictions.

![feature_impt](Images\feature_importance.png)

![top3features](Images\top3_features.png)

* Instrumentalness - This value represents the amount of vocals in the song. The closer the instrumentalness value is to 1.0, the greater likelihood the track contains no vocal content. 
* Tempo - Tempo is the speed or pace of a given music and derives directly from average beat duration. 
* Energy - Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy

### c. Process Map
1) Data was split using train_test_split
2) Scaled using standard scaler
3) Utilised OneHotEncoder to fit y_train
4) Initiated neural network model
5) Added 2 neural layers
6) Compiled & fitted
7) Included 10% of our training data as validation data to obtain x_val & y_val accuracy
8) Comparing it to our test data accuracy

We further optimised the accuracies the neural model by altering the number of neural layers, no. of epochs.

![validation_accuracy](Images\validation_accuracy_loss.png)

The model came to a steady state after 60 epochs with the following results:

* val_accuracy = 0.9136
* val_loss = 0.2365
* test_accuracy = 0.8376
* test_loss = 0.6086

The fact that val accuracy is higher than test accuracy suggests that the hyperparameters in this model have been specifically tuned for this specific validation dataset. A bigger sample size might be needed to improve this. 

## 4. How to Use This Repository
1) Raw data was collated via spotipy package "01 playlist_export_function.ipyb". Simply just input your username & spotify URI and it will churn out that specific playlist together with its audio features.

2) "03 final_neural" is where the neural network model is set up. 





