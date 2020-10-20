---
layout: post
title:  "Ideas Update"
date:   2020-10-19 19:25:43 +0100
categories: blog post
---

# Ideas Update

There was a change of plans. Meetings with supervisors have been delayed, so we are to pick a project and start work on the proposal before discussing the initial ideas.

My main proposal will be for the pronunciation focussed language application (as it's probably the project I am most personally invested in), however, I will do research into the feasibility of one of the other ideas just in case.

The Main challenge for the language application will be the database setup - keeping global ranks of word  and sentence difficulty as well as individual ones for each user.

I have been looking into graph databases for another project and started wondering how one could work here - it may be advantageous to use one to model the relations between words and sentences - however common words may end up with too many relations - which could slow the system or break it.

I think a conventional SQL or no-SQL database will still be needed to store user information and might still be the right choice overall.

There are several more things that need researching and deciding also:

1. Platform: Web app or Native android app (leaning towards web app / PWA)
2. Collecting sentences: preferably with audio, or look into google text-speech
3. How to split up sentences: into words ignoring conjugation (or not)
4. Decisions on what statistics to gather globally and for the user
5. What fields words and sentences will need to rank them and serve them to users (weightings)
6. How to run initial analysis on words/sentences - possibly word frequency - but perhaps also compile lists of known difficult words and push up those words (to appear more likely)
7. Identify user groups can the program be tested with and how it should be done
8. Decide on language support in development (currently thinking Japanese and English, but might do French or Spanish also which a lot of people may have learnt at some point increasing the people able to test the app on...)
9. Can you use two database types and make them work nicely together?
10. ???

So, lots to do!