---
layout: post
title:  "Collection update and looking at some spikes"
date:   2021-03-27 20:27:34 +0100
categories: blog post





---

Collection continues and is going well. The script has worked fairly robustly, however there is the occasional error with tweet collection, with either the message "over capacity" or "rate limit exceeded". I have looked up the error codes and they seem to be down to the twitter API restricting access when too busy. There may be a way around it and I'm looking for ways to handle it automatically, either by abandoning collection and restarting later, or pausing for a while.

Below is a graph of the hourly tweet collection so far:

![]({{site.baseurl}}/img/hourly-tweets-to-27-3.png)

And below is the daily polarity (with zero values removed):

![]({{site.baseurl}}/img/daily-polarity-to-27-3.png)

Hopefully soon I plan to run some models to work out if the sentiment data with or without zeros have stronger correlations. I also need to work out if it's sensible to re-merge the 'shared' tweets back into the Bitcoin and Ethereum tweets. I will test them un-merged, however because the Dogecoin tweets do not have any tweets filtered out, it will probably be best to merge them back in for the sake of model comparison (but I could always try filtering out tweets containing other cryptocurrency hashtags after collection to make things consistent that way instead).

### Looking at some spikes

I've been looking through some of the data collected so far and some of the major events outlined in the last blog post are definitely evident in the volume spikes. Such as the Tesla Bitcoin purchase announcement on  8th Feb.

Some spikes aren't explainable by news though. I was looking for explanations in the large spikes in Ethereum on 13th Feb and 15th March, but couldn't find any particular news which would explain them. I looked at the tweet files for those dates and found quite a lot of spam tweets (posted in a small time-frame) promoting other cryptocurrencies (YNI by the Yearnifi network and stackio stack tokens). A lot of the tweets were identical, however quite a few had minor variations. These promotional tweets might explain the spikes.

I had set the sentiment methods to drop any tweets with duplicate text before processing, however I will need to double check if this is taking place as expected. If it is filtering duplicates out and it's the minor variations of the promotional messages causing the spikes, I will probably leave them in for consistency.

I am in two minds as to whether trying to filter out spam identical, or spam tweets from the volume data is a good idea. However I may look further into the topic if I have some time.

### Major News Since last post:

24th March - Tesla now accepts payment in Bitcoin for cars [link](https://www.bbc.co.uk/news/technology-56508568)

