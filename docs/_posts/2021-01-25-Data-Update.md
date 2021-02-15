---
layout: post
title:  "Data Update + general"
date:   2021-01-25 17:39:04 +0100
categories: blog post





---

Just a quick progress update.

#### Tweet data

I have been collecting tweets using the TAGS method and have experimented using the official API and Tweepy.

The API access I have been given seems to allow me to collect 500,000 tweets every month, which should be enough to collect a fairly decent sample.

As mentioned in the previous post the TAGS method is preferable as I don't have to keep my computer running to use it and from the data collected so far I think it should work fine, however I will also start running Tweepy daily to collect around 10,000 tweets.

This should act as a fail-safe If I encounter any issues in processing the TAGS tweets later down the line.

Currently I am collecting tweets containing the hashtags #Bitcoin and/or #Ethereum. I think I will stick to these two coins for the project, however I will make the final decision whether to look at a 3rd coin (or more) this weekend.

I will also commit the (hopefully finalised) Tweepy scripts to the main repo on the weekend.

#### Twitter Volume data

Finding sources of volume data has been surprisingly difficult. I haven't been able to find a better source than [bitinfocharts](https://bitinfocharts.com/comparison/tweets-btc.html#3m) since the last post on twitter data.

Most searches return websites and services set up to help users explore the impact of campaigns involving hashtags and have quite steep pricing associated.

Bitinfocharts does seem to have the right data, but with no obvious way to export it. There may be a way to extract it, but I haven't found one so far. An article by [Tigo Vidal on cointelegraph](https://cointelegraph.com/news/how-traders-can-use-twitter-to-anticipate-bitcoin-price-moves-volume) also used data from bitinfocharts, so there may be a way.

I will continue looking for a source for daily tweet volume, preferably as a call to an API of some sort, however in the worst case it should only take a few hours to manually copy over data from the charts on bitinfocharts.

### Other / General

Price data has been relatively easy to find, both historically and current. With the methods of collecting tweets pretty much finalised my focus will now switch to processing the price data and training my first model on some section of it.

At this stage this will essentially be testing, but will help establish the data pre-processing procedure and having a starting model should help with developing baselines, model comparison and with making the GUI for displaying model results.

I will be trying to make blog posts a bit more frequently from now on with a status update once a week. The longer posts on research and results will either remain separate from the status updates, or be integrated in... as yet undecided...

