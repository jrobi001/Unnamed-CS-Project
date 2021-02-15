---
layout: post
title:  "Gathering twitter data"
date:   2020-11-29 21:47:15 +0100
categories: blog post



---

Gathering twitter data could end up being one of the more challenging aspects of the project.

As it is not the focus of the project, it would be good to find a fairly 'hands off' solution that does not eat up too much time better spent elsewhere.

The amount of data that can be collected determines the types of analyses that can be performed. In general there are two analyses that can be done, both requiring different amounts of data:

1. **Sentiment Analysis**: This requires a good representative sample of data, in other words a fairly decent proportion of relevant tweets, though not necessarily all.
2. **Volumetric Analysis**: This would require the collection of every tweet and tabulation by day or hour. This may not be feasible (without spending a lot of money for API access), however there are other sites and services that give tweet volumes by hashtag, which could be used instead.

From researching methods; collecting a complete set of related tweets for a good time period is unlikely. In all likelihood I will be attempting to collect a good sample of tweets for sentiment analysis over a 60-90 day time period, then rely on external data sources for volumetric data.

Below I run through some of the options for collecting twitter data. Some blog posts and tutorials are also included mainly for my future reference (or for anyone also interested):

## Twitter API methods (offical)

### Twitter API and Tweepy

Twitter's official API is the obvious option, however the limits placed on the free tiers of access are quite low. The premium APIs remove many caps, however also have a steep access cost associated.

A cost example: $149 for up to 500 requests a month, with 500 tweets per requests = 250,000 tweets.
↳ This seems like a lot of data, however if you consider the hashtag '#bitcoin' gets anywhere from 30-80,000 tweets a day, it only translates to a few days worth of tweets.

Twitter does provide a more generous free API for students and researchers (subject to approval). I have applied for access and if granted this may provide sufficient data for sentiment analysis, however it does still have some drawbacks:

- Tweets per request and caps are still in place, restricting totals
- The free caps are generally per hour or 15 mins, meaning a script (and computer) would need to be running 24/7 to not loose out on data collection

Tweepy is a python is a python library which makes working with the twitter API much easier and should allow fairly easy integration with scripts for data backup and the processing of tweets gathered

https://elfsight.com/blog/2020/03/how-to-get-twitter-api-key/

https://developer.twitter.com/en/solutions/academic-research

https://developer.twitter.com/en/docs/developer-portal/twitter-for-education

https://www.tweepy.org/

### Twitter streaming API

The twitter streaming API was generally designed to allow live feeds of tweets (on certain topics) to be displayed on websites (or in apps). It provides a live (stream) of tweet data.

In theory this stream of data can be captured and processed by scripts to input tweets into a database (or file).

Access comes with a developer account and the pricing is unclear from the documents provided. From blogposts it seems the streaming API returns anywhere between 1% and 40% of the total tweets posted, depending on activity.

One paper mentioned the streaming API which received a feed of data that could be entered to a database (if set up right)

https://developer.twitter.com/en/docs/tutorials/consuming-streaming-data

### Twitter Firehose

A stream of data which returns 100% of tweets posted, however costs lots and lots of money.

In theory this would be perfect for the project, It would require a reliable PC with constant connection, but barring any downtime it would collect 100% of the tweets for the period run.

### TAGS

TAGS collects tweets based on search results and collects them into a google sheet. It can be setup to run every hour. TAGS can run using a provided API key, but also has an option not using one.

In general each request returns around 3000 of the most recent tweets. Given the number of tweets per day to the #bitcoin hashtag this may be anywhere from 30 mins - 2 hrs worth of tweets

The immediate advantage is that this system can be left running without need to keep a computer constantly running.

TAGS does not claim to be able to return a full set of tweets and there is some likelihood that different requests may return duplicate tweets, requiring some processing to eliminate them.

It is as yet unclear whether there are advantages or disadvantages in providing TAGS with an API key.

https://tags.hawksey.info/get-tags/

## Twitter scraping methods (unofficial)

The value of twitter's data is immense and the free API only provides a small portion of data. Many scraping methods and techniques which gather data bypassing the official API exist and may provide larger portion of data.

### TWINT - Twitter Intelligence Tool

TWINT is a scraping tool, it does not rely on the API and as such does not share the API's limits. Scrapers generally rely on pretending to be a normal user, scrolling through feeds and collecting information.

It may not provide as much metadata with each tweet as official methods utilizing the twitter API.

https://github.com/twintproject/twint

https://null-byte.wonderhowto.com/how-to/mine-twitter-for-targeted-information-with-twint-0193853/

## Sources for volumetric data + other 

Some sites collect data on the daily tweet volume of hashtags associated with cryptocurrencies - it may be possible to export their datasets (for use in training) or to find where they source their data to do volumetric analysis.

https://bitinfocharts.com/comparison/bitcoin-tweets.html#3m

## Google trends data

While not twitter data, google trends gives information on how often a search term is used. It provides the numerical count of the search term usage broken down in various time intervals  worldwide downloadable as a CSV.

This data is similar to volumetric twitter data in displaying interest. It may be useful to use as an alternative or in conjunction with twitter data

https://trends.google.com/trends/explore?date=today%201-m&q=bitcoin

## Summary and conclusions

There are quite a few methods to access twitter data, some more hands on than others.

At this point I will be implementing several of the methods and inspecting the outputs of leaving them running to see which is best for the task.

Currently I plan to use:

- Conventional twitter API - I have applied for both normal and academic access and await the response, I will use this with tweepy and with TAGS
- TAGS, I plan to leave both a sheet not signed in with my twitter API key and one with my key and compare the results.
- TWINT, it is worth running this system to see if it provides a greater volume of tweets, the potential of metadata loss is not so important.
- External sources for volumetric data. It has become clear from research that reliably capturing 100% of tweets without spending a lot of money is very unlikely even if I dedicate a lot of time to the process. I will use one of the methods above for collecting a sample of tweets for sentiment analysis then try to gather volumetric data elsewhere