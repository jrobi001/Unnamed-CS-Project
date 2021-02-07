---
layout: post
title:  "Tweet collection update"
date:   2021-02-07 17:40:07 +0100
categories: blog post

---

# Tweet collection update

So official collection started on the 1st, but the snscrape/tweepy method has been running since the 31st Jan, giving us 7 days of tweets so far.

I decided to extend the collection of tweets to #eth and #btc and combine them with the tweets gathered for #ethereum and #bitcoin respectively. This means the shared tweet files now contain tweets containing `(#eth OR #ethereum) AND (#btc OR #bitcoin)` or something similar~

This has led to a slightly increased rise in the number of Ethereum tweets gathered (which was the aim).

Below are the results from the first 7 days of collection:

| Date       | Bitcoin | Ethereum | Shared |
| ---------- | ------- | -------- | ------ |
| 2021-01-31 | 25848   | 2148     | 4554   |
| 2021-02-01 | 35133   | 3924     | 5921   |
| 2021-02-02 | 32269   | 9256     | 5963   |
| 2021-02-03 | 34317   | 8616     | 6585   |
| 2021-02-04 | 33859   | 7114     | 6565   |
| 2021-02-05 | 37508   | 7361     | 6245   |
| 2021-02-06 | 39264   | 5382     | 5742   |

Also I decided to start collecting tweets on Dogecoin, recent events were too interesting to ignore and it could be interesting to monitor. For now these tweets are being kept separate with no checking for shared tweets with other hashtags. I am not yet certain I'll use them in the analysis later on.

#dogecoin and #doge tweets were collected on Thursday 4th Feb looking backwards. From most accounts Tweet collection is generally reliable looking about 7 days back, however I collected 10 days back to capture the days before huge rise that occurred on the 28th/29th Jan (meaning that the earliest three counts should be taken with a grain of salt).

| Date       | Dogecoin |
| ---------- | -------- |
| 2021-01-25 | 766      |
| 2021-01-26 | 946      |
| 2021-01-27 | 1574     |
| 2021-01-28 | 77286    |
| 2021-01-29 | 244706   |
| 2021-01-30 | 73858    |
| 2021-01-31 | 50858    |
| 2021-02-01 | 36374    |
| 2021-02-02 | 19990    |
| 2021-02-03 | 20805    |
| 2021-02-04 | 60669    |
| 2021-02-05 | 30432    |
| 2021-02-06 | 35042    |

Quite a huge peak on 29th!

I was not expecting the snscrape/tweepy method of being capable of collecting such a huge quantity of tweets in a single call!

This has changed how I thought the collection method works, previously I thought calls were limited to about 30-40k tweets each, however now it seems like it's capable of collecting a lot more. I am not sure why the numbers are lower than the statistics on bitinfocharts.com, but the difference is reliable, with each day's total being around 3-4 times less than their totals. I am not sure whether this means a reliable fraction of tweets is being captured, or if this really is the full volume of tweets and the figures on bitinfocharts.com are unreliable.... some further investigation will need to be done... 🤔

Overall this is promising though and reliable, with tweet collection automated to a single script run. I may modify the methods used to make them more generally applicable, but that will probably be on a different branch or repo, as for now the script works!

The TAGS method is also working well as a backup, I will need to create ways of processing those CSV files to analyse whether or not they are collecting more tweets than the tweepy method.

### Other / general

The images from the last blog post on the first model did not load, I will look into this and perhaps work on the blog layout a little. 

In future weeks I won't post the tweet totals like above, but maybe graphs of the collection of tweets over time as part of a weekly blog update.

