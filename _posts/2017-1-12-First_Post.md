---
layout: post
title: MTA Turnstile Data
---

My first project at Metis involved a hypothetical scenario in which a client focusing on fundraising for the promotion of women in tech wanted to make use of MTA turnstile data in order to maximize the collection of email addresses from passers-by by making use of street teams positioned at subway stations throughout NYC.

## Defining the the objective ##
The problem statement was quite open-ended, and my instructors pointed out that in real-life instances clients often look to you, the data scientist, for guidance on how best to tackle a certain problem. With that in mind, my team (Karl Rudeen and Max Kneissl) and I set out to specifically define the objective of our work so that both the client and ourselves would know exactly what we would be producing.

>Objective: Provide WTWY with a selection of locations at given subway stations in order to maximize the collection 
of email addresses by allocated volunteers primarily using MTA turnstile data and additional data sources.

## Data cleaning and exploration ##
Sadly, in the real world data is often messy.  The MTA turnstile data is no different, despite being a relatively straightforward dataset.  Our first task was to inspect the data and identify potential issues with the validity of the values.  One issue we ran into was coming up with a count of passengers within a given interval of time (e.g. per day) due to the fact that counts in the data set are given in 4 hour blocks that occasionally overlap into the next day (e.g. window between 11pm and 3am), in addition to being inconsistent across the different measurement units.  We addressed this problem by simply looping over the data and subtracting the earliest count from the latest count for each day.  Although this led to some possible underestimation, we deemed it to be acceptable for the purposes of our analysis given the likely low traffic in the middle of the night.
