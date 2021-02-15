---
layout: post
title:  "Tweet collection started + update"
date:   2021-02-02 18:03:35 +0100
categories: blog post






---

Both methods of tweet collection were finalised and officially started on Feb 1st.

So far tweets with #bitcoin or #ethereum are being collected.

The Tweepy method uses [snscrape](https://github.com/JustAnotherArchivist/snscrape) to gather tweet URLs then fetches those tweets using the twitter API, outputting a CSV. CSV's are split into 3 files, one for #ethereum exclusive tweets, one for #bitcoin exclusive tweets and a third for tweets containing both #ethereum and #bitcoin.

This process runs collecting tweets from the day before and only take 10-20mins.

Below are the first two days returns of the Tweepy script:

| Date       | #Ethereum (only) | #Bitcoin (only) | Both hashtags |
| ---------- | ---------------- | --------------- | ------------- |
| 2021-01-31 | 2148             | 25848           | 2278          |
| 2021-02-01 | 2695             | 31009           | 2500          |

I am considering making a final alteration to also collect tweets containing #btc and #eth.

In the case of Ethereum the tweet count returned is low and a lot of tweets are shared with bitcoin. Looking through twitter #eth seems the preferred hashtag to #ethereum for most users.

---

The TAGS method is collecting a lot more tweets, since the 31st it has collected 45,000 #ethereum tweets and 146,948 #bitcoin tweets, which according to the charts on [bitinfocharts](https://bitinfocharts.com/comparison/tweets-btc-eth.html#3m) is nearly all of them. I am slightly worried about duplication and the potential need for extra processing from this method, but it could return close to a full set. 

I am also slightly worried that it operates outside my control, I won't know if it stops working or if the google sheet is filled until I check on it some time later, but for now it seems to be working well. 

Google sheets has a limit of 5 million cells, which worries me. I may need to download and clear the bitcoin sheet every day or two, which may cause duplicate tweets to be collected requiring processing. However this shouldn't be too bad...

---

Either way, with both methods set up and collecting, I should hopefully have good redundancy if one fails! 🎉

### General update/plans

Tomorrow I will be working on pre-processing one set of price data for use in a ML model, then running it through a basic LSTM, hopefully all goes well! 😅





