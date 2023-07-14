# Twitter-Finance-NLP
## Business Understanding
**StakeHolder**: A **regular investor** who is following financial news on Twitter
- The regular investor has been using Bloomberg and other main stream financial news centers to get stock information
- They are looking to get an edge on most investors but are having trouble finding out how
- They find that there is a lot of financial buzz is on Twitter
- However, they are having trouble deciphering whether the tweets are neutral, bullish or bearish
    - This can be helpful to know when to buy, sell, short, or keep an eye on for future investments
**The Goal:** build a machine learning model using a natural language processor to identify whether a tweet is bullish, bearish or neutral
- It can be used for the investors needs  their next to identify their next big play in the market
- Equally it can make the investor privy to when stocks will potentially plummet

## Data Understanding
- The dataset was found on [Hugging Face](https://huggingface.co/datasets/zeroshot/twitter-financial-news-sentiment)
- The Twitter Financial News dataset is an English-language dataset containing an annotated corpus of finance-related tweets. 
- This dataset is used to classify finance-related tweets for their sentiment.
- The size of the dataset is roughly 12,000 rows of text
- The data contains two columns; a text column that contains the tweet text and a corresponding label column with a sentiment.
    - Sentiments
         - Label 0: Bearish
         - Label 1: Bullish
         - Label 2: Neutral

## EDA/Data Preperation

- Did some exploratory data analysis on the target variable to see if their was a class imbalance

![image](https://github.com/ddcots24/Twitter-Finance-NLP/assets/131708046/66e7e620-396f-4b0e-9153-ae48d53a427e)

**Class Imbalance!** This is important to know before I start modeling.


- I also looked at the most common words used for each label

![image](https://github.com/ddcots24/Twitter-Finance-NLP/assets/131708046/b30dba1b-83ee-42a2-a743-dfeddf6c06cc)
![image](https://github.com/ddcots24/Twitter-Finance-NLP/assets/131708046/d0ace2e3-e2c5-4309-ac7e-9e33ec0f95bb)
![image](https://github.com/ddcots24/Twitter-Finance-NLP/assets/131708046/e4904879-734b-41f3-865a-8ac8e4a68e67)

- The similar words such as "stock" and "market" make sense as the most common words across all three labels
- Notable words in Bearish: "miss", "cut", "low"
- Notable words in Bullish: "beat", "high"
- Notable words in Neutral: "say", "report", "result"

## Modeling

- Took an iterative approach with modeling
- Started with complement naive bayes
- Then did random forest
- Best model was xgboost classifier
    - With a f1_weighted score of 81%

**Confusion Matrix**

![image](https://github.com/ddcots24/Twitter-Finance-NLP/assets/131708046/dc8868bf-0183-4657-b66b-48d386147e05)

- Taking a look at the confusion matrix and evaluting model accuracy, the model makes a good amount of mistakes deciphering if a bullish/bearish tweet is neutral
- It is pretty good at picking if a tweet is neutral
- It is decent at identifying if a tweet is a bullish label when compared to bearish label and vice versa

**Feature Importances**

![image](https://github.com/ddcots24/Twitter-Finance-NLP/assets/131708046/14daad4c-783a-4bff-a449-8375653562c0)

**Important!** Each feature is a word in the CountVectorizer and there is over 11,000 words which is why the feature importance percentage is so low


## Evaluation

- The best model is the XGBoost classifier with an overall f1_weighted score of 81%
- I chose the f1_weighted score as the overall metric performance because we want to take into account of the class imbalance
- f1_weighted metric takes in the f1 score for each label and returns the average considering the porportion of each label in the dataset
- In the case of the stake holder the consequence of error is equally as strong in recall and precision score which it is why the f1 metric is the best option
    - This is miss information and will lead to poor investment decisions
- Overall I dont think this model is good enough to use in the real world as it has some issues identifying the bullish and bearish labels

## Recommendations

- Focusing on captains of the financial industry. The opinions and recommendations of these influencers can gain insights into market sentiment and potentially follow their trading strategies.
- Risk management: high amount of bearish sentimental tweets in a stock that you are invested in, set up stop loss orders
- Day trading: if a company's earnings report is released, analyze the sentiment of tweets related to that event to gauge the market's reaction. This can provide additional insights into short-term price movements and potential trading opportunities.


