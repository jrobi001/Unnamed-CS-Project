---
layout: post
title:  "Price collection using Santiment API and Code Re-Writes"
date:   2021-04-20 15:44:12 +0100
categories: blog post





---

### Santiment API

I have been testing around with the santiment API using the [sanpy](https://github.com/santiment/sanpy) python module and all seems to work well. The API offers hourly historical data for all the currencies I'm looking at and although there was little mention of the free API (and the access it gives) before signing up, it seems like it is quite generous. The sanpy module also makes working with the data incredibly easy, as results are returned as pandas DataFrames, ready to be saved as CSVs.

One thing to note is that calls using sanpy are limited to a complexity of 20,000 items, with each feature such as open, close, volume etc. counting as a feature. It may be necessary to create a method that splits requests up to 1 month or so, when making the final calls.

I plan to integrate price collection from santiment with the tweet collection script soon, collecting the prices up to the day before, to go along with the tweets collected up to the day before.

### Code Re-writes

As mentioned a few posts back I'm planning to re-work my code to make it more usable and re-usable.

First steps will be modifying the sentiment and analysis methods to work on a single cryptocurrency at a time and perform both the hourly and daily analysis at the same time. Then I'll need to remove the hard-coding of the cryptocurrencies from the collection script as well, so that any cryptocurrencies could be passed in to the methods.

After those are done, I plan to first just copy all the content of each of the current main scripts into one large script to confirm things work. Once it does I can think about splitting the main script into main functions, or other ways to clean up the code.

Currently I am thinking about how to handle user defined cryptocurrencies. I could create a class and associate the main methods with that cryptocurrency class, however a lot of the methods don't necessarily feel like they belong to the class. I could create classes for the various files at various stages, or for the various tools, like snscrape or Tweepy, but I think this adds more complexity than necessary.

I could use this as an opportunity to delve more into object oriented methodology, however I think the code would be a lot clearer, just creating cryptocurrency objects without methods attached, then keep the methods related to different tasks segmented in folders/modules as they currently are.

Not sure, will see~~