---
layout: post
title:  "General progress update"
date:   2021-01-09 21:08:17 +0100
categories: blog post





---

Revision period is underway and unluckily I've had a string of colds and headaches since the surgery last month, but the worst of it seems to be over.

Below I'll run through some of the things I've been up to that don't necessarily warrant their own blog posts.

### Twitter data

I've set up the TAGS twitter scraper mentioned a couple of weeks back, it is collecting tweets with either of the hashtags #bitcoin or #ethereum. I'll be monitoring the tweets gathered over the next week or so and will evaluate what it collects. In terms of practicality this methods is preferable over the other options, however I plan to implement and compare the results gathered from several methods over the next week or two.

The twitter data source needs to be finalised fairly soon. Most methods can only return tweets from around 7 days prior. This means that in order to gather data over a long enough time frame for the machine learning models to work on collection will need to start soon. Ideally 60-90 days would be good, which means the collection process needs to be underway by the end of the month by the latest.

### Front end / GUI / web app

I have done a some more research into creating a web app for presenting the model results and possibly live data. I am fairly confident it can be achieved using the Node.js express framework I am familiar with using node modules that allow for python files to run. I will look into this further at a later date and if necessary switch over to using a python web framework like flask, or to a python desktop app using a GUI.

For now I have set up a basic Node.js express environment in the main repository linked to a MySQL database that can be used for testing. I plan to try and use one of the models built in my AI module and try setting it up to display in the web app some point soon. It would be good if the front end could be developed alongside the development of the cryptocurrency models rather than trying to do it all at the end after the models are finalised.

### ML Models to use

From looking papers solving similar tasks the most popular model types used on timeseries data like stocks and cryptocurrency prices are RNN and LSTM models. Some of the older papers use other non-deep learning techniques. While there will be quite a lot to explore using just RNN and LSTM models I plan to spend a while longer looking to see if there are any other deep learning or machine learning techniques that may be applicable.

However I am conscious that if I try and use too many model types things may get out of hand and may take time away from improving existing models or comparing them. If possible I would like to create models that use:

- Price data alone to make predictions
- Price data and twitter (and/or google trends) volumetric data
- Price data and twitter sentiment data
- Price data and both volumetric and sentiment twitter data
- (possibly) a model only using twitter data alone (and processed price data as a targets in training) which predicts if prices go up or down the following day