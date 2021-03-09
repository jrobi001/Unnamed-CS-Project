---
layout: post
title:  "Tweet Statistics and Sentiment"
date:   2021-03-04 18:07:11 +0100
categories: blog post




---

So collection is ongoing, as of `03-03-2021` 2,877,886 tweets have been collected, averaging to about 95k a day!

The issues with 'bad tweets' has been resolved, the culprit was the 'carriage return' `\r` and was only used in a very small number of tweets. It is now being filtered out at collection time, so should no longer be an issue.

I have done some further breakdowns of the tweets so far in terms of volume and have also and analysed the tweets sentiment using textblob (on a daily timescale). I may look at other methods of sentiment analysis better suited to twitter language, but the textblob results seem adequate.

### Tweet volume plots

![]({{site.baseurl}}/img/03-03-21-hourly_tweet_count.png)

![]({{site.baseurl}}/img/03-03-21-breakdown-tweetcount.PNG)

As mentioned before the periodicity of the data is encouraging, suggesting a reliable portion of the tweets are being collected each day (and that my volume data could be used rather than relying on an external source, though this requires further investigation/analysis).

### Tweet sentiment plots

When running the textblob sentiment analysis there were a large volume of tweets which received a zero score for either or both polarity and subjectivity. This is largely due to a large number of tweets being mostly comprised of hashtags, links and mentions (which are filtered out in the analysis). A lot of these posts are spam. I decided to determine scores both including these 'zero score' results and without them. Currently I can't tell which is more reflective of the data, but It may be worth training models on both sets of data and comparing the results.

![]({{site.baseurl}}/img/03-03-21-daily_polarity_w_zeros.png)

![]({{site.baseurl}}/img/03-03-21-daily_polarity_without_zeros.png)

![]({{site.baseurl}}/img/03-03-21-Daily_subjectivity_w_zeros.png)

![]({{site.baseurl}}/img/03-03-21-daily_subjectivity_without_zeros.png)

### Cryptocurrency plots

Just for comparison here are the cryptocurrency prices of the coins for the same period

![]({{site.baseurl}}/img/03-03-21-crypto-prices.PNG)

