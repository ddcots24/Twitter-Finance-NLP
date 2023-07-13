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
