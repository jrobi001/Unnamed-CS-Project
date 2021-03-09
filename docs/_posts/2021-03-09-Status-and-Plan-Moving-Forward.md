---
layout: post
title:  "Status and Plan Moving Forward"
date:   2021-03-09 18:47:05 +0100
categories: blog post





---

With much of the groundwork done collecting and processing twitter and price data, It is now time to shift focus to the main aspect of this project - the running and analysis of ML models on this data.

There are still a few data processing and background tasks to finish, mainly:

- Create sentiment score breakdown by hour (by adapting existing daily breakdown function)
- Create tweet volume breakdown by day  (by adapting existing hourly breakdown function)
- Integrate price, sentiment and volume data - either into a CSV, or design methods to do so (also ensuring that the time zones/times of the price and twitter data line up)
- Convert some data processing tasks into helper functions
- (not essential) General code clean-up for re-usability and addition of docstrings

These will be done alongside the running of ML models on the data. For the next week or two I will be focussing on models run on price data alone, but by the end of next week I want to have tried training a model on the hourly price data with twitter data as well.

There are a fair number of tasks ahead. Apart from the refining of models, there are some other tasks which will need attention:

- Create plots of model predictions to visualise performance (beyond loss values)
- Research/define methodology of comparing models with each other
- Create a common-sense baseline model
  - Probably either 'the price tomorrow is the same as the price today', or 'the trend in price change over the past 'X' days will continue' (with X being 7, 30, 90 or some other sensible number of days)
- Decide whether to / implement hyperparameter tuning method to test many variations of the same model at once.
- Better/nicer visualisations in matplotlib generally and/or exporting data and attempting to create nice visualisations in D3.js
- Implementing/running ML models other than LSTM and RNN (maybe KNN?)
- (stretch goal) display results in a web app and have best models running on live data

Then of course there's the research and writing for the report. The first draft is due in two and a half weeks. Until then I will be prioritising the tasks which allow me to gather preliminary results.

Lots to do, lots to do~~