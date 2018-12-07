# 480-Final-Project

# Amazon Bid Cities Analysis

## *Research Question, Background, and Problems*

Our research problem is to determine how residents in Long Island City, NY and Crystal City, VA feel about Amazon building a facility in their cities. 

Many cities advocated to win the bid for Amazon to build their facility in their city, citing economic advantages and increased employment opportunities. However, there has been some speculation about whether the residents of these areas are actually supportive of their local government’s decision to allow Amazon to build in their cities. We aim to determine the sentiment of the residents in these cities in regard to the arrival of Amazon.

The problem identified is that while winning Amazon headquarters was highly valued amongst cities across the United States, it is unclear as to whether or not the residents of Crystal City and Long Island City welcome Amazon coming to their city and why or why not. 

## *Data Collection and Preperation*

In order to answer our question, we collected tweets from Crystal City, Virginia and Long Island City, NY that were discussing Amazon Headquarters. We used the following parameters to collect tweets from both locations:

### **Collection Parameters**
#### *Crystal City, Virginia*
- Coordinates = (38.8554° N, 77.0521° W) 
- Search Radius = 50 miles
- Keywords = Amazon HQ, Amazon headquarters, HQ2
- limit = 1000

#### *Long Island City, New York*
- Coordinates = (40.7447° N, 73.9485° W) 
- Search Radius = 50 miles
- Keywords = Amazon HQ, Amazon headquarters, HQ2
- limit = 1000

### **Collection Process on RapidMiner**
<img src="Data Collection Process.PNG" width="900">

### **Collection Output**
Using the parameters listed above, we collected 1217 tweets from Crystal City, Virginia and 699 tweets from Long Island City, New York. The data collected from Virginia was split into [test](https://github.com/vipariox/480-Final-Project/blob/master/VA%20Test%20data.xlsx) and [training](https://github.com/vipariox/480-Final-Project/blob/master/VA%20Training%20Data.xlsx) data and the data collected from New York was split into [test](https://github.com/vipariox/480-Final-Project/blob/master/NY%20Test%20Data.xlsx) and [training](https://github.com/vipariox/480-Final-Project/blob/master/NY%20Training%20Data.xlsx) data using a 7:3 test to training ratio. 
<img src="Data Collection Bar Graph.PNG" width="700">

## *Classification Models*

### Naive Baye's Model

#### Preparing the Data
To prepare our data fro Naive Bayes we labeled the tweets in the [Virginia Training Data](https://github.com/vipariox/480-Final-Project/blob/master/VA%20Training%20Data.xlsx) and the [New York Training Data](https://github.com/vipariox/480-Final-Project/blob/master/NY%20Training%20Data.xlsx) as supportive, unsupportive, or neutral in regard to their feelings towards the arrival of Amazon. Then the trianing data and test data is appended together, cleaned, and stored as a database in RapidMiner that can be retrieved for the Naive Bayes Model application.
<img src="Clean tweets process.PNG" width="900">

#### Naive Bayes RapidMiner Process
<img src="Naive bayes process.PNG" width="900">

#### Naive Bayes Output - Virginia
The excel output for the Virginia Naive Bayes model can be found [here](https://github.com/vipariox/480-Final-Project/blob/master/VA%20Naive%20Bayes%20Output.xlsx). Below is a screenshot of the output of prediction classification of Virginia tweets. 
<img src="VA Naive Bayes prediction output.PNG" width="900">



#### Naive Bayes Output - New York
The excel output for the New York Naive Bayes model can be found [here](https://github.com/vipariox/480-Final-Project/blob/master/NY%20Naive%20Bayes%20Output.xlsx). Below is a screenshot of the output of prediction classification of New York tweets. 
<img src="NY Naive Bayes Prediction output.PNG" width="900">

#### Naive Bayes Output - Virginia versus New York
When comparing the prediciton outsomes of both locations, it can be seen that most of the tweets collected from New York are predicted to be neutral and tweets collected from Virginia are predicted to be unsupportive.
<p float="left">
  <img src="NY Naive Bayes Prediction output Bar Graph.PNG" width="400" />
  <img src="VA Naive Bayes Prediction output Bar Graph.PNG" width="400" />
</p>

### K Means Clustering Model 

#### K Means Rapid Miner Process

<img src="K means process.PNG" width="900">

#### K Means Output - Virginia
<img src="VA K Means supportive word clouds.png" width="800">
<img src="VA K Means unsupportive word clouds.png" width="800">

#### K Means Output - New York
<img src="NY K Means Supportive Word Clouds.png" width="800">
<img src="NY K Means Unsupportive Word Clouds.png" width="800">

## Justification of Selected Models and Data Parameters

### Naive Bayes
We decided to use the Naive Bayes model in Rapidminer as the primary model to solve our problem due to its ability to classify text well, resulting in better sentiment analysis. The bulk of our data dealt with the classification of tweets as supportive or unsupportive, with a neutral category used to help furher sort unrelated tweets. With enough tweets, Naive Bayes can semi-accurately classify tweets based on a relatively small set of training data by utilizing the frequency of certain words in tweets, making it an ideal model for the type of sentiment analysis our project focused on. 

### K-Means Clustering
We used K-Means clustering in Rapidminer as a means of secondary analysis after utilizing Naive Bayes. Once Naive Bayes sorted the predicted tweets as supportive or unsupportive, K-Means clustering best allowed us to further sort the words within all the tweets in each classification based on groups of similar words. Based on the tweets collected and the nature of the sentiment analysis conducted, this model best helps us gain insight into the reasons people tweeting may have been supportive or unsupportive. 

### Data Parameters

## Conclusions, Limitations, and Suggestions
