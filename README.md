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

## EDA

- Did some exploratory data analysis on the target variable to see if their was a class imbalance

![image](https://github.com/ddcots24/Twitter-Finance-NLP/assets/131708046/66e7e620-396f-4b0e-9153-ae48d53a427e)
**Class Imbalance!** This is important to know before I start modeling.

- I also looked at the most common words used for each label

![image](https://github.com/ddcots24/Twitter-Finance-NLP/assets/131708046/b30dba1b-83ee-42a2-a743-dfeddf6c06cc)
![image](https://github.com/ddcots24/Twitter-Finance-NLP/assets/131708046/d0ace2e3-e2c5-4309-ac7e-9e33ec0f95bb)
![image](https://github.com/ddcots24/Twitter-Finance-NLP/assets/131708046/e4904879-734b-41f3-865a-8ac8e4a68e67)

- The similar words such as "stock" and "market" make sense as the most common words across all three labels
- 
