## Title: National patterns in race tweets

**Problem:** Racial bias is difficult to measure due to its sometimes ambiguous and subtle presentation. Most empirical measures of racial bias or discrimination are conducted using individual self-reporting or experimental testing that attempts to obtain results using indirect or subconscious actions. A research study being conducted at UCSF, Department of Epidemiology & Biostatistics, is using Twitter data to create place-level measurement of sentiment towards racial/ethnic minorities. The study analyzes more than one million U.S. tweets related to race/ethnicity for sentiment. A sample of the tweets (6,600) have been human-labeled with 90% agreement between the researchers. The researchers have made the data available to me to help them classify the tweets as positive, negative, or neutral. A previous study was conducted using sentiment analysis, but they were unable to classify the tweets into more than two categories. They got around this by collapsing the neutral category into the negative category. This project will be my attempt to use machine learning NLP methods to classify the tweets into the three categories originally proposed by the researchers.

**Data:** A stata file was obtained from Thu Nguyen, a post-doctoral fellow (Associate Specialist) at UCSF, Department of Epidemiology & Biostatistics. It contained the original tweets, along with results from a previous sentiment analysis, names of the people who hand coded the data (conducted after the unsupervised sentiment analysis), the labels, and the state, county, and zip code for the location of each tweet. Each tweet has an identification number attached as well as a location FIPS code that was determined from the latitude and longitude locations from the tweets. The FIPS code will be used to create the U.S. heatmap by county after the final prediction. The training set has 6,481 rows, each with one tweet. The unlabeled set to be predicted is 1.25 million tweets, of which the training set was extracted for manual labeling last summer. 

The tweets were obtained from March 2015– April 2016 using Twitter’s Streaming Application Programming Interface (API) to continuously collect a random sample of publicly available tweets. This API gives access to a random 1% sample of tweets. The data was restricted to only tweets with latitude and longitude coordinates for the contiguous United States and the District of Columbia. In total, there are 79,848,992 million general topic tweets from 603,363 unique Twitter users in the dataset.  A keyword list of 398 racial/ethnic group terms and slurs was derived from racial and ethnic categories used by the U.S. Census and the online database of racial slurs. These keywords were used to identify tweets that contained at least one race-related word. This resulted in 1.25 million tweets. 
Out of this, the training set was created by randomly selecting a subset of 6,481 tweets for manual labeling. Three coauthors labeled three possible responses: negative or positive.  Inter-rater reliability among the coders was 90% for sentiment rating.  In addition, the labelers indicated whether the tweet used discriminatory or stereotyping language about a racial group, whether the tweet mentioned a non-food location (e.g., Jewish Center), and whether the tweet should be excluded because it was not race-related (relating to individuals, people, or culture).

**Approach:** A previous sentiment analysis was conducted using the Stochastic Gradient Descent Classifier in Python software version 2.7. This is a linear classifier that has the value “0” or “1” and is appropriate for classifying into only two groups. To accommodate these restrictions, the researchers joined the neutral category with the negative category as this gave more accurate results in preliminary analyses. The purpose of my study is to develop machine learning classification algorithms that will classify tweets into three categories: positive, negative, or neutral.


**Deliverables:** Code: data visualization, exploratory data analysis, machine learning algorithms, predicted and classified Tweets. Report on the project. Presentation.


**References:**
Caruana, R., & Niculescu-Mizil, A. (2006). An empirical comparison of supervised learning algorithms. Proceedings of the 23rd International Conference on Machine Learning - ICML '06. doi:10.1145/1143844.1143865

Sentiment analysis. (2018, December 10). Retrieved from https://en.wikipedia.org/wiki/Sentiment_analysis

Smetanin, S. (2018, September 01). Sentiment Analysis of Tweets using Multinomial Naive Bayes. Retrieved from https://towardsdatascience.com/sentiment-analysis-of-tweets-using-multinomial-naive-bayes-1009ed24276b
