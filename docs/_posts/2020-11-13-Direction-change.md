---
layout: post
title:  "Direction change"
date:   2020-11-13 15:34:23 +0100
categories: blog post
---

# Direction Change

The reading and practice pronunciation application is likely too much work for the development period, especially if implementing 2 languages to demo it to other people. Also the work that would go into scheduling sentences and words may not be immediately obvious to those looking at it.

For this reason I am now deciding between two project ideas:

1. A location based forum application that uses geofences do define forum boundaries in the real world.
2. An investigation into using Machine Learning to predict cryptocurrency price changes using previous price data, as well as twitter data.

I should hopefully make a decision on which project to pursue early next week. Below are more detailed descriptions of each:

### 1 - Location based forum / message board

A location based forum/message board. It will be an android app (or PWA) that uses the phone's location to detect if the user is inside the geographical boundaries of user-created message boards and display the messages posted.

The idea is that users or organisations can set up message boards that display posts to other users within that location. A couple of example use cases:

1. At a music festival or conference set the area as the location allowing visitors to post things or event organisers to send out information only to those actually in attendance. The app could possibly also work as a live chat or as a way to ask only those in the audiences questions at events rather than on twitter
2. Travelling to Lands End, Stonehenge or a small town somewhere, open the app and see what other people have posted while they were there, possibly see posts from local business owners or residents about events that might be going on or from other visitors to that area
3. As a simple local forum, maybe for a town, a street, an office or a lecture hall, people there could make posts about things going on

### 2 - Predicting Cryptocurrency Prices Using Machine Learning and Twitter Data

A cryptocurrency application that will investigate the predictive power of machine learning on previous price data and twitter activity related to cryptocurrencies, to see if price predictions can be made on different time scales.

The standard mantra for traditional stock markets is that they behave too irrationally for machine learning to be reliable, however machine learning predictions may still perform better than the traditional trend algorithms that are generally overlaid on stock trading applications.

Cryptocurrencies work a little differently from stocks and their prices may be much more reliant on peoples interest and the current hype surrounding them. I am interested to see whether predictions can be made on previous price data alone by comparing predictions from different machine learning techniques and whether predictions that take into consideration tweet volume and sentiment analysis related to cryptocurrencies could do any better (or worse).

If a good predictive power is achieved from twitter activity it may also be interesting to investigate whether there are clusters of users that are particularly influential. Clusters could be identified by running community detection algorithms on tweet data imported to a graph database such as neo4j. Analysis here could also potentially identify bots or users attempting to influence cryptocurrency prices on twitter.

After training the networks, the application will visualise the current predictions for different cryptocurrencies based on the current data, which may be useful as a tool for cryptocurrency traders, much like the traditional algorithmic trend predictors that can be overlaid in various stock trading applications.

Most of processing scripts will be written in Python using techniques such as web-scraping, data cleaning, data mining, deep learning, machine learning and neural networks.

The resulting data would be stored in a database, the app interface and visualisations would likely be written to run as a web application using Javascript, Node.js, mongodb, angular and d3.js