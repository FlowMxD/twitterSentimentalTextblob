import tweepy

from textblob import TextBlob



consumer_key = 'NzzHYXxcgBQBstp7oz2rX5f0q'
consumer_secret = 'RvHNkZX1qFBm7LCYrH0QfMMddiKAOythyezcm2IwYbXSFl4TFj'

access_token = '3170614980-3qVA6VwCiir7VKqO0LaIzOFPRetJoq3A2NOviTX'
access_token_secret = '20phgJIZyKCcMO1uHeJzl7otEanoJKK7YtGdCHdARjjf3'

auth = tweepy.OAuthHandler(consumer_key,consumer_secret)
auth.set_access_token(access_token,access_token_secret)

api = tweepy.API(auth)

public_tweets = api.search('car')

for tweet in public_tweets:
    print(tweet.text)
    analysis = TextBlob(tweet.text)
    print(analysis.sentiment)
