# Sentiment analysis using Twitter

* Sentiment analysis is a technique that involves extracting opinion from text
* A sample use cause can be using tweets from Twitter to discover people feelings about a product or service
* Helps find polarity \(positive or negative\)
* Data sources: Review sites, blogs, forums, social media, etc.
* Text data can either be facts \(mostly neutral\) or opinions \(consists of polarity\)

### Sentiment Analysis method <a id="Sentiment-Analysis-method"></a>

1. Rule based
   * Matching words with sentiment scores from a lexicon \(sample of words with associated polarity scores\)
   * No training required
   * Not so accurate
2. Automatic
   * Trained pattern matching algorithm will predict a word's sentiment
   * Uses machine learning such as classification algorithm to find polarity
   * More accurate and scalable
   * Needs more training data

### Sentiment analysis using Twitter API and Vader python framework

#### Step 1: Create a Twitter application to access twitter data <a id="Step-1:-Create-a-Twitter-application-to-access-twitter-data"></a>

* URL: [https://developer.twitter.com/en/apps/create](https://developer.twitter.com/en/apps/create)

#### Step 2: Get keys and access tokens to access twitter API <a id="Step-2:-Get-keys-and-access-tokens-to-access-twitter-API"></a>

* consumer\_key = ''
* consumer\_secret = ''
* access\_token = ''
* access\_token\_secret = ''

#### Step 3: Install dependencies <a id="Step-3:-Install-dependencies"></a>

```python
!pip install pandas
!pip install tweepy
!pip install vaderSentiment
```

#### Step 4: Import dependencies <a id="Step-4:-Import-dependencies"></a>

* Tweepy: Accessing data from Twitter
* Vader: For sentiment analysis

```python
import tweepy
import pandas as pd
from nltk.sentiment.vader import SentimentIntensityAnalyzer

# gather lexicon data
import nltk
nltk.download('vader_lexicon')
```

#### Step 5: Search for tweets <a id="Step-5:-Search-for-tweets"></a>

```python
# Twitter API authentication variables
consumer_key = 'Insert here..'
consumer_secret = 'Insert here..'
access_token = 'Insert here..'
access_token_secret = 'Insert here..'
```

```python
# authentication
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)

# Twitter API
api = tweepy.API(auth)

# search for 'Indian Surgical Attack'. Ignore retweets
tweets = api.search('Indian Surgical Attack -filter:retweets', count=200)

# extract tweet text and create a single column data frame
data = pd.DataFrame(data=[tweet.text for tweet in tweets], columns=['Tweets'])

# display top 10 tweets
display(data.head(10))
```

```text
	Tweets
0	The Pakistani Army deployment, including radar...
1	Indian Air Force Air Strike on Jaish's Terror ...
2	When India Said Pak did:\n\n2008 Mumbai Attack...
3	@Tirthan96689171 @ReutersWorld Here we r nt di...
4	First insult martyrs by calling Pulwama Terror...
5	@TimesNow @RShivshankar This shows that @INCI...
6	''The Indian voters will lead the third surgic...
7	When India Said Pak did:\n\n2008 Mumbai Attack...
8	When India Said Pak did:\n\n2008 Mumbai Attack...
9	When India Said Pak did:\n\n2008 Mumbai Attack...
```

**Note:** The response from tweepy search\(\) contains metadata information of tweets.

```python
# metadata extracted by tweepy
# https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/tweet-object
print(tweets[0].text)
print(tweets[0].created_at)
print(tweets[0].source)
print(tweets[0].retweet_count)
```

```text
The Pakistani Army deployment, including radars and air defense system along the LoC, was strengthened immediately… https://t.co/EiLUBi7Wgc
2019-03-12 23:30:00
TweetDeck
11
```

#### Step 6: Perform sentiment analysis using Vader <a id="Step-6:-Perform-sentiment-analysis-using-Vader"></a>

```python
# Sentiment analyser
sid = SentimentIntensityAnalyzer()

list = []
for index, row in data.iterrows():
    sentiment_score = sid.polarity_scores(row['Tweets'])
    list.append(sentiment_score)
ss_series = pd.Series(list)

# create a new column 'polarity' with the corresponding sentiment score
data['Polarity'] = ss_series

# display the first 10 elements
display(data.head(10))
```

```text
	Tweets	                                            Polarity
0	The Pakistani Army deployment, including radar...	{'neg': 0.0, 'neu': 0.777, 'pos': 0.223, 'comp...
1	Indian Air Force Air Strike on Jaish's Terror ...	{'neg': 0.353, 'neu': 0.647, 'pos': 0.0, 'comp...
2	When India Said Pak did:\n\n2008 Mumbai Attack...	{'neg': 0.437, 'neu': 0.563, 'pos': 0.0, 'comp...
3	@Tirthan96689171 @ReutersWorld Here we r nt di...	{'neg': 0.0, 'neu': 1.0, 'pos': 0.0, 'compound...
4	First insult martyrs by calling Pulwama Terror...	{'neg': 0.502, 'neu': 0.498, 'pos': 0.0, 'comp...
5	@TimesNow @RShivshankar This shows that @INCI...	{'neg': 0.239, 'neu': 0.761, 'pos': 0.0, 'comp...
6	''The Indian voters will lead the third surgic...	{'neg': 0.154, 'neu': 0.846, 'pos': 0.0, 'comp...
7	When India Said Pak did:\n\n2008 Mumbai Attack...	{'neg': 0.437, 'neu': 0.563, 'pos': 0.0, 'comp...
8	When India Said Pak did:\n\n2008 Mumbai Attack...	{'neg': 0.437, 'neu': 0.563, 'pos': 0.0, 'comp...
9	When India Said Pak did:\n\n2008 Mumbai Attack...	{'neg': 0.437, 'neu': 0.563, 'pos': 0.0, 'comp...
​
```

