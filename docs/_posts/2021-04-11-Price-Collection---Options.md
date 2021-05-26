---
layout: post
title:  "Price Collection - Options"
date:   2021-04-11 19:02:57 +0100
categories: blog post




---

Up until now I've been relying on [cryptodatadownload.com](https://www.cryptodatadownload.com/) for historical price data on cryptocurrencies. This has worked fine so far however I cannot find any source for Dogecoin hourly price data on the site and quite a few of the datasets I have downloaded have missing hours and some duplicated data. I have searched for other sites which provide hourly prices in CSV format, but had no luck.

My original plan was to gather historical data from cryptodatadownload, then If I finished the website implementation, fetch current data by hourly API calls. However, I now feel it makes much more sense to find another source for historical (and current) price data that can be combined with the tweet collection and analysis script. Hopefully it should be possible to combine the tweet analysis data with collected price data and to automatically generate datasets that can be used in the ML models. (And hopefully the other source will have Dogecoin Hourly price data).

### Options

**APIs:** There are quite a few cryptocurrency APIs, which provide current and historical price data. As seemingly with a lot of APIs the information on how many requests are provided in the free plans are vague. I think I will try implementing one or two and see if the free API access allows me to collect the amount of data I need. Since I only need hourly data for 3 coins over a 90 day period I may need as few as 6480 API calls to just get the close prices. If none of the APIs offer what I need for free I will probably try web-scraping the prices. If that fails I may sign up for one of the APIs free trial periods towards the end of the project to collect the data (though hopefully it won't come down to that).

Brief list of options that could work:

https://neuro.santiment.net/

https://api.tiingo.com/

https://www.coinapi.io/

https://p.nomics.com/cryptocurrency-bitcoin-api

https://cryptowat.ch/

**Scraping:** I have come across quite a few tutorials running through using tools like [Beautifulsoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) to scrape historical price data from sites like CoinMarketCap.com. An advantage of using a scraper would be that one less API access token would be needed by my application and no API pricing problems. The one issue is that I am not certain if I can collect hourly data using scraping. It may be worth searching more and seeing if it's possible, however I think an API is a safer bet for now.