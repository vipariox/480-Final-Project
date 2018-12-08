# Resident Analysis of Amazon HQ2 Cities

## *Research Question, Background, and Problems*

Our research problem is to determine how residents in Long Island City, NY and Crystal City, VA feel about Amazon building a facility in their cities. 

Many cities advocated to win the bid for Amazon to build a facility in their city, citing economic advantages and increased employment opportunities. However, there has been some speculation about whether the residents of these areas are actually supportive of their local government’s decision to allow Amazon to build in their cities. We aim to determine the sentiment of the residents in these locations in regard to the arrival of Amazon.

The problem identified is that while winning Amazon headquarters was highly valued amongst cities across the United States, it is unclear as to whether or not the residents of Crystal City and Long Island City welcome Amazon coming to their city and reasons why or why not. 

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
Using the parameters listed above, we collected 1217 tweets from Crystal City, Virginia and 699 tweets from Long Island City, New York. The data collected from [Virginia](https://github.com/vipariox/480-Final-Project/blob/master/VA%20Collected%20Data.xlsx) was split into [test](https://github.com/vipariox/480-Final-Project/blob/master/VA%20Test%20data.xlsx) and [training](https://github.com/vipariox/480-Final-Project/blob/master/VA%20Training%20Data.xlsx) data and the data collected from [New York](https://github.com/vipariox/480-Final-Project/blob/master/NY%20Collected%20Data.xlsx) was split into [test](https://github.com/vipariox/480-Final-Project/blob/master/NY%20Test%20Data.xlsx) and [training](https://github.com/vipariox/480-Final-Project/blob/master/NY%20Training%20Data.xlsx) data using a 7:3 test to training ratio. 
<img src="Data Collection Bar Graph.PNG" width="700">

## *Classification Models*

### Naive Baye's Model

#### Preparing the Data
To prepare our data fro Naive Bayes we labeled the tweets in the [Virginia Training Data](https://github.com/vipariox/480-Final-Project/blob/master/VA%20Training%20Data.xlsx) and the [New York Training Data](https://github.com/vipariox/480-Final-Project/blob/master/NY%20Training%20Data.xlsx) as supportive, unsupportive, or neutral in regard to their sentiment towards the arrival of Amazon. Then the trianing data and test data is appended together, cleaned, and stored as a database in RapidMiner that can be retrieved for the Naive Bayes Model application.
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
When comparing the prediciton outcomes of both locations, it can be seen that most of the tweets collected from New York are predicted to be neutral and tweets collected from Virginia are predicted to be unsupportive.
<p float="left">
  <img src="NY Naive Bayes Prediction output Bar Graph.PNG" width="400" />
  <img src="VA Naive Bayes Prediction output Bar Graph.PNG" width="400" />
</p>

### K Means Clustering Model 

#### Preparing the Data
In order to prepare the data for the K Means cluserting, we seperated the both excel outputs from the Naive Bayes model into [Virginia supportive data](https://github.com/vipariox/480-Final-Project/blob/master/VA%20Naive%20Bayes%20output%20supportive.xlsx), [Virginia unsupportive data](https://github.com/vipariox/480-Final-Project/blob/master/VA%20Naive%20Bayes%20output%20unsupportive.xlsx), [New York supportive data](https://github.com/vipariox/480-Final-Project/blob/master/NY%20Naive%20Bayes%20Output%20Supportive.xlsx), and [New York unsupportive data](https://github.com/vipariox/480-Final-Project/blob/master/NY%20Naive%20Bayes%20Output%20Unsupportive.xlsx). By seperating the tweets into seperate excel files based on location and predicted sentiment, we can use the K Means model to cluster tweets within these categories to gain better insight into different reasons *why* people are supportive or unsupportive of Amazons new locations. 

#### K Means Rapid Miner Process

<img src="K means process.PNG" width="900">

#### K Means Output - Virginia
<img src="VA K Means supportive word clouds.png" width="800">
 Cluster Themes

- Cluster 1: local citizens and the effect on housing
- Cluster 2: News media showcasing the development of the headquarters
- Cluster 3: Specific well known people that may be supportive
- Cluster 4: local schools and education

Output Data
- [Virginia Supportive Clusters](https://github.com/vipariox/480-Final-Project/blob/master/VA%20K%20Means%20Clustered%20Tweets%20-%20Supportive.xlsx)

<img src="VA K Means unsupportive word clouds.png" width="800">
 Cluster Themes

- Cluster 1: political deals/corruption 
- Cluster 2: effects on specific areas of VA and their residents
- Cluster 3: effect on local infrastructure and housing
- Cluster 4: references to NY

Output Data
- [Virginia Unsupportive Clusters](https://github.com/vipariox/480-Final-Project/blob/master/VA%20K%20Means%20Clustered%20Tweets%20-%20Unsupportive.xlsx)

#### K Means Output - New York
<img src="NY K Means Supportive Word Clouds.png" width="800">
 Cluster Themes
 
 - Cluster 1: no pattern
 - Cluster 2: effects on business
 - Cluster 3: local economy
 - Cluster 4: Comparing NY to Silicon Valley
 
 Output Data
- [New York Supportive Clusters](https://github.com/vipariox/480-Final-Project/blob/master/NY%20K%20Means%20Clustered%20Tweets%20-%20Supportive.xlsx)

<img src="NY K Means Unsupportive Word Clouds.png" width="800">
 Cluster Themes
 
 - Cluster 1: no pattern
 - Cluster 2: local schools/politics
 - Cluster 3: local economy
 - Cluster 4: NY politicians/politics
 
 Output Data
- [New York Unsupportive Clusters](https://github.com/vipariox/480-Final-Project/blob/master/NY%20K%20Means%20Clustered%20Tweets%20-%20Unsupportive.xlsx)

## Justification of Selected Models and Data Parameters

### Naive Bayes
We decided to use the Naive Bayes model in Rapidminer as the primary model to solve our problem due to its ability to classify text well, resulting in better sentiment analysis. The bulk of our data dealt with the classification of tweets as supportive or unsupportive, with a neutral category used to help furher sort unrelated tweets. With enough tweets, a Naive Bayes model can be trained to classify tweets based on a relatively small set of training data by utilizing the frequency of certain words in tweets, making it an ideal model for the type of text analysis our project focused on. 

The main parameters that were set was the ratio of test to trinaing tweets. We initially used a ratio of 9 test tweets to 1 training tweet, but later realized that was not enough training tweets for the test data to be accurate. We then changed the ratio to a 7 to 3 ratio, which allowed for more accurate prediction without requiring too much manual data entry, given the short time frame we had.

### K-Means Clustering
We used K-Means clustering in Rapidminer as a means of secondary analysis after utilizing Naive Bayes. Once Naive Bayes sorted the predicted tweets as supportive or unsupportive, K-Means clustering  allowed us to further sort the words within all the tweets in each classification and location based on groups of similar words. Based on the tweets collected and the nature of the sentiment analysis conducted, this model best helps us gain insight into the reasons peoples tweets were supportive or unsupportive. 

The default max runs ended up working for our project, as any changes did not yield any discernable results. We used 4 as our k value, giving us enough variety to identify a few different clusters of possible tweet topics. Generating more than 4 clusters resulted in clusters with too few words to discern a general theme.

## Conclusions, Limitations, and Suggestions

### Conclusions
The results for this project indicate that the sentiment towards Amazon's placement of the 2 new headquarters is mostly negative or neutral in both locations. NY had less people tweeting about the new headquarters and a much larger percentage of tweets that were neutral or irrelevent, which is interesting due to the larger population density of NY compared to VA. VA was overwhelmingly unsopprtive of the new headquarters, with several references to the NY headquarters, indicating that VA is more vocal about the topic and the placement of the headquarters in VA may have more consequences than in NY. The overall conclusion is that while policticians and some business leaders may have been fighting for Amazon to come to their city, the everyday twitter user was not in favor of such actions. 

### Limitations
The biggest limitation was the nature of social media. While twitter can give us a snapshot, it does not speak for the entire population: not everyone who has an opinion is going to tweet about it. Additionally, it may be the case that only people who are upset at Amazon are going to tweet about it to vent their frustration, giving our data a negative bias that does not reflect the actual sentiment in that location. The models are also not perfect: many irrelevant words and tweets could not be filtered out and may have skewed the models' predictions and clusters. Lastly, while some tweets were clear in the support or lack thereof, some tweets were more ambiguous, requiring a judgement that could have some amount of inherent bias or subjective reasoning. 

### Suggestions
Some possible ways to improve this analysis would be to take more time collecting a larger number of tweets and using a larger training set while carefully labeling the training data. While this may be more labor intensive, it could yield much more accurate predictions and could be managed by a slightly larger team. Also incorporating more methods to process the data would result in more useful words and tweets being analyzed while sorting out many of the irrelevant and nonsensical words that plagued our data. 
