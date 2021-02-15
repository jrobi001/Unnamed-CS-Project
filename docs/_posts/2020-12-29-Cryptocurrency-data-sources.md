---
layout: post
title:  "Cryptocurrency data sources"
date:   2020-12-29 18:42:32 +0100
categories: blog post




---

There are quite a few possible sources of cryptocurrency data, it does not seem like gathering this data will be too difficult a process or take too much time.

There are a few things to consider:

- The currency being converted from/to. For the purpose of this report I will likely stick to USD conversion prices as this is most prevalent.
- Second is that quite a few of the data sources break down historical prices by individual exchanges, It may be necessary to look into the data provided from each exchange.
- If plan to switch from historic data to live data from APIs Ideally the data should be from the same exchange or source and the same data categories should be available 

### Historical Data

**[Coindesk](https://www.coindesk.com/price/bitcoin)** : Provides historical data in CSV for most major coins. This data is only every 24 hrs and contains open, close, 24hr high and 24hr low data. It does not mention any exchange specifically.

**[cyptodatadownload.com](http://www.cryptodatadownload.com/data/)**: Provides the historical data of different coins from various exchanges. The amount of data depends on the exchange, but the Bitstamp exchange provides daily, hourly and minutely data. The data from Bitstamp contained open, close, high, low and volume in BTC and USD data

**[bitcoincharts.com api CSVs](https://api.bitcoincharts.com/v1/csv/)**: Also provides the historical data of various exchanges, the bitstamp csv downloaded did not have labelled columns, but it may be worth looking at others

These seem to be the best candidates for historical data, though there may be others. Of the three cyrptodatadownload.com is the most promising offering breakdowns by hour and day.

### Live data

I have come across several APIs which allow for the price of coins to be checked. I will need to sign up for access to each of them and inspect the data they return to see if they are compatible with historic data before deciding on one. This is all provided I have enough time to attempt and run the models on live data.

From the pricing information all should provide enough free requests a day. The determining factor will be the data each returns. This will probably be returned to in a later blog post

Options:

https://www.coinapi.io/

https://p.nomics.com/cryptocurrency-bitcoin-api

https://coinmarketcap.com/api/

https://min-api.cryptocompare.com/

https://www.coingecko.com/en/api