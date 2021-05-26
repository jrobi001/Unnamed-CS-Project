---
layout: post
title:  "Final Report and Project decisions"
date:   2021-04-04 11:42:09 +0100
categories: blog post





---

So the final report is coming up and time is marching on. I have my last two coursework assignments due in the next couple of weeks, then hopefully I should be able to dedicate more time to the project.

I have been looking at the final report sections and thinking about my project. Up until now I was just building the tools I need for the project as I need them and a fairly modular manner, the tweet collection scripts separate from the data processing scripts etc. I was originally planning to then use the models created and post them (possibly) running live on a website, which would be my implementation, however I don't think I will have time for that.

If I don't have time, my implementation will likely be the data collection and processing scripts and the work I do creating models and predictions. With the shift of focus of the implementation to the data-collection and processing side of things, I think I will need to spend some time improving the reliability and usability of my code and possibly integrate it into a single script which can be used by others.

This will involve removing all code which hard-codes the cryptocurrencies being looked at and the collection dates, as well as providing settings that users can update without needing to look through the code. I will probably also need to put in warnings and procedures to handle data collection problems, such as the script being closed in operation, or if collection isn't performed for several days.

I'll also need to set up the repo or create a release where the settings are at default values and provide instructions for setting it up for the first time.

I would still like to try to implement some sort of basic web page to display some results, but I think re-structuring my code and setting it up for re-usability is a good idea whatever happens.