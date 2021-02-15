---
layout: post
title:  "General Update + Reading Week"
date:   2021-02-14 17:32:43 +0100
categories: blog post


---

### Tweet collection - 2 week update

So tweet collection continues below is an updated tweet count table and graph for the first two weeks:

| Date        | Bitcoin     | Ethereum   | Shared     | Dogecoin    |
| ----------- | ----------- | ---------- | ---------- | ----------- |
| 2021-01-31  | 25848       | 2148       | 4554       | 50858       |
| 2021-02-01  | 35133       | 3924       | 5921       | 36374       |
| 2021-02-02  | 32269       | 9256       | 5963       | 19990       |
| 2021-02-03  | 34317       | 8616       | 6585       | 20805       |
| 2021-02-04  | 33859       | 7114       | 6565       | 60669       |
| 2021-02-05  | 37508       | 7361       | 6245       | 30432       |
| 2021-02-06  | 39264       | 5382       | 5742       | 35042       |
| 2021-02-08  | 88060       | 5615       | 7300       | 59868       |
| 2021-02-09  | 60804       | 5650       | 7167       | 35838       |
| 2021-02-10  | 52403       | 6359       | 7096       | 30664       |
| 2021-02-11  | 46220       | 4957       | 6729       | 22099       |
| 2021-02-12  | 40824       | 5844       | 6700       | 20613       |
| 2021-02-13  | 33265       | 10477      | 5852       | 15113       |
| 2021-02-14  | 40374       | 6397       | 6367       | 17029       |
| **TOTALS**  | **600148**  | **89100**  | **88786**  | **455394**  |
| **AVERAGE** | **42867.7** | **6364.3** | **6341.9** | **32528.1** |

![]({{site.baseurl}}/img/2-weeks-Tweepy.png)

Promising so far, the method seems to be working well. The graph also shows the same general trends that the graph on [bitinfocharts.com](https://bitinfocharts.com/comparison/tweets-btc-eth-doge.html#3m) shows (with some minor variations probably caused by time zones and day classifications). The trends are the same, but the totals are quite massively different, as mentioned before I need to do a little more digging to work out who's numbers are more reliable for use in volume analysis... (if both have the same trends, once normalised potentially either source may be fine to use?)

The tweets gathered from the snscrape/tweepy method seem predominantly fine and ready to use, however I have come across a couple of tweets which seem to break the formatting of the CSV. I will need to work on methods of  identifying, processing and removing these:

![]({{site.baseurl}}/img/broken-formatting.png)

The TAGS method is also running, as I worried before the bitcoin sheet hits the cell limit on google sheets roughly every 2-3 days (of normal tweet volume), but it is working fine as a backup in case anything goes wrong with the snscrape/tweepy method.

### Next Steps

There's lots to do, but here's a general list in somewhat priority order:

- Create methods of processing tweet CSV's:
  1. To remove duplicates and handle badly formatted tweets
  2. Pre-processing, ready for entry into sentiment analysis model
- Decide on method of sentiment analysis on tweets. Perform analysis both daily and hourly?
- Create helper functions out of data preparation methods in first model
- Research and create commonsense baselines for models to beat
- Research and create methods of comparing models against each other
- Maybe link up the sentiment analysis to run on the tweets straight after collecting them and output results to a new CSV
  - Clean up methods in sncrape/tweepy and make them more general
- Try displaying visualisations of model outputs in D3.js
  - In node.js
  - Maybe could experiment with a Django web server?