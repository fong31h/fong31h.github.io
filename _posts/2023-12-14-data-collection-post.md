---
layout: post
title:  "Musical Artists: Data Collection and Cleaning"
author: Spencer Fong
description: A documentation of the data collection process for my Stat 386 final project
image: "/assets/images/taylorswift.jpeg"
---

### Examining the Numbers on Music (Data Collection and Cleaning)

## Intro

Music is something that we don't think about too often in our day-to-day life and yet plays a big role in both our personal lives and in our culture and society. With this project I hope to examine in greater depth what factors could lead to artists becoming popular.

In this blog post I will be explaining my process for collecting the data that I will use later for analysis.

## Data Collection Process

# Step 1: The API

The first step was finding a place where I could collect data on artists. I searched for different APIs and websites that would have information and eventually I found the last.fm API which fit my needs perfectly. Then, before beginning the API calls I first had to take time to understand the documentation. There were a lot of different options for calls to make, but eventually, I decided that the best method would be to requests the data on around 350 'top artists', as defined by last.fm.

# Step 2: Getting the Data

The next step was actually writing a call that could get me the data that I needed. This required two steps. The first step was to request the names of the top artists and putting them all into one list. The next step was to use that list to call the individual artists information for each one. One for loop and lengthy API call later, I had a list with each entry filled with a wealth of artist information.

# Step 3: Cleaning the Data

This is when the real work began. The data was structured in an intricate, multi-layered tangle that required extensive testing and exploration in order to understand. Each artists info was contained inside a dictionary, which contained another dictionary, which contained a list of dictionaries, which contained more dictionaries (that's not even an exaggeration). With the help of for loops and list comprehensions, I eventually managed to get the majority of it into a data frame. One aspect though, genre, was particularly tricky. I'll spare the gory details, but I eventually had to heavily limit the possible genres and choose only three for each artist.

Unfortunately, the last.fm API was missing two pieces of information that I felt would be very useful for analysis: sex, and age. I ended up using wikipedia to get this information manually, which took a couple of hours.

# Step 4: Ethical Considerations, Conclusion, Link

Fortunately for this project, I mainly used an API that was freely available to the public, so there are no ethical worries in using this data.

In conclusion, it was a challenging process that required some creativity to wrangle the data into a usable form. It was gratifying to see the completed data frame at the end though.

Here is a link to the GitHub repository. The code for reading in and wrangling the data is under 'Semester Project.ipynb', the data is found in 'artists.csv'.

<a href="https://github.com/fong31h/Stat386_Final_Project" target="_blank">Stat 386 Final Project</a>