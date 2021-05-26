---
layout: post
title:  "Missing Price Data and Code Refactoring Plan"
date:   2021-05-01 21:33:57 +0100
categories: blog post






---

### Missing Price Data

On inspection it seems some hourly price data is missing from the Santiment API. Calls using different metrics also returned the same missing data.

Only dates missing data from collection period are on `2021-02-01` and `2021-02-02`.

### 2021-02-01 missing times:

Dogecoin: 17:00 to 23:00

Bitcoin: 17:00, 18:00, 20:00 to 23:00

Ethereum: 18:00, 21:00 - 23:00

### 2021-02-02 missing times:

Dogecoin: 00:00, 01:00, 03:00, 05:00, 06:00, 07:00

Bitcoin: 00:00, 02:00, 03:00, 06:00, 07:00

Ethereum: 00:00 to 07:00

### Solutions

It isn't Ideal, but since these are the only two dates affected and they are right at the beginning of the collection period, I will shift the start of the dataset to `2021-02-03`. I will still have a 90 day collection period with this data.

As mentioned in a previous post, the data from cryptodatadownload.com also had missing data, so this may be a fairly widespread problem due to server downtime or something similar.

Alternatives would be:

1. Manually find data from these times from other sources (which may add inconsistencies)
2. Create placeholder values averaged from the values immediately before and after
   - Though the longer missing periods could cause issues.
3. Remove these hours/data points from the the twitter data also and only run on the times collected
4. Implement another API to collect historical price data and either fill in the affected dates with data from these dates, or re-collect the whole set of data from those APIs (and check the data is complete again)

For now I will carry on, planning to use data from 3rd Feb onwards and implement checks on the consistency of data when collecting, or when combining. Hopefully I can implement a method to create a dataset from the longest period of complete data collected automatically.

If there is time I will test a couple of other cryptocurrency APIs one evening and see if they give complete sets of data without any missing values (or if the price data is the consistent across the APIs and can be filled in manually or automatically).

### Code Refactoring Plan

I have decided against trying to re-work the code into classes, I do not think it will improve readability. Instead I will use YAML files to store user settings and information on the cryptocurrencies the user wishes to collect tweets/data on. I will convert the cryptocurrencies from the YAML files into simple objects and use them that way.

I read several blog posts on the correct ways of organising python projects. They differed slightly, but I tried to follow some of their guidelines. Generally I will leave related methods in folders/modules, create a main file which calls them (one folder up, `main_methods.py`) then create a shorter file which imports the settings and runs that file in the main data collection directory `main.py`.

It probably doesn't conform to correct methods, but this is the structure I've come up with:

```
final-project-cryptocurrency
|- ml_notebooks
|- datasets
|- data_collection
|   |- auth
|   |	|- api_auth.yml
|   |- data
|   |   |- raw-tweet-data
|   |   |- snscrape-archive
|   |   |- processed-tweet-data
|   |   |- tweet-sentiment-files
|   |   |- price-data
|   |- src
|   |   |- price_collection
|   |   |- twitter_scraper
|   |   |- tweet_csv_processing
|   |   |- combine_data
|   |	|- main_methods.py
|   |- main.py
|   |- settings.yml
|   |- cryptocurrencies.yml
```

If I have time towards the end I may spend some more time reading about project structure and try creating setup files and possible implementing other things.

If I can work out how to create a release version or something with placeholder values in files like the API authorisation file it would be good also.

(also need some way to make sure folders exist, could put a placeholder text in each folder, or implement checks for `if folder not exists => create directory` in the setup)