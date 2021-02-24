---
layout: post
title:  "Tweet CSV processing - trials and tribulations"
date:   2021-02-22 20:06:13 +0100
categories: blog post



---

### The tribulations

So one of my major recent aims was to process the tweet CSVs ready for sentiment (and possibly volumetric) analysis.

Both are now done and ready to do, however it was quite an ordeal. The solution is fairly simple, but getting there was another thing.

The main problem encountered were tweets with *'bad'* formatting. The tweets were almost universally spam, with a link to some website followed by a line break or two and a message. 

The problem is that the line-breaks used in them do not seem to use the escape character `\n`. Those characters are already being filtered out during tweet collection. The undetected line breaks caused the formatting of the CSV to offset resulting in either the CSV not being importable to a pandas dataframe, or for all tweets below the bad tweet to be offset by a column or two  (not very helpful).

The number of these bad tweets was proportionally very low, they only came from 2-3 users and in most files there were only about 25-15 tweets, however in a couple there were a lot more, specifically in the doge coin tweets where one file had over 100 (all spam from the same few users).

Two weeks of tweets had already been collected so I needed a way to remove these tweets. There were few enough that it could be done manually, but I didn't feel like having to do that every couple weeks.

I initially tried various methods of detecting the tweets in a pandas dataframe and removing them, this worked but led me to discovering the tweets which offset all the tweets below - resulting in 1000s of tweets being removed. I then tried deleting only those tweets identified by this method manually, which worked, fixing the tweets below (but  was manual~). After doing that I encountered some tweets which prevented the forming of a pandas dataframe on a couple of files. I could have set a counter to identify the exact tweet that broke it and deleted manually, but I decided to try another way.

I eventually decided processing using pythons inbuilt CSV reader and writer methods would probably be more sensible. I spent a while hunting in bad tweets what exactly caused them to break, but couldn't find any special/escape characters using `repr()`. I then decided to go line by line and detect any tweets that don't start with an ID string, which nearly worked (leaving the start of half complete tweets). This led me to my final solution just to go line by line checking that the number of columns is the same for each entry and deleting any tweets that had the wrong number.

This solution is nice and simple, fixes all the issues and as the 'bad' tweets are rare (and also spam), I'm not too worried that their removal will affect any results dramatically.

In the future I plan to re-collect and inspect the 'bad' tweets, directly from the API, to try and work out what about them is causing the issue and whether it can be mitigated at collection time.

### The good

The good news is that's over with, it works and now the CSV's can be processed for analysis or running through sentiment models.

As a first analysis I decided to count the tweets per hour and plot them (below).

![]({{site.baseurl}}/img/tweets-per-hour.png)

The same technique should be usable if want to analyse sentiment or volume on an hourly basis. If looking at volume, it may be possible to normalise the data based on all the previous volumes at that time or just the past few days. The periodicity of tweets per hour data gives me more confidence that we are collecting a reliable portion of the total tweets each day.