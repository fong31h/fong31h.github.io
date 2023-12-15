---
layout: post
title:  "Musical Artists: Data Collection and Cleaning"
author: Spencer Fong
description: A documentation of the data collection process for my Stat 386 final project
image: "/assets/images/taylorswift.jpeg"
---
![last.fm](/assets/images/lastfmlogo.png)
## Examining the Numbers on Music (Data Collection and Cleaning)

### Intro

Music is something that we don't think about too often in our day-to-day life and yet plays a big role in both our personal lives and in our culture and society. With this project I hope to examine in greater depth what factors could lead to artists becoming popular.

In this blog post I will be explaining my process for collecting the data that I will use later for analysis.

### Data Collection Process

### Step 1: The API

The first step was finding a place where I could collect data on artists. I searched for different APIs and websites that would have information and eventually I found the last.fm API which fit my needs perfectly. Then, before beginning the API calls I first had to take time to understand the documentation. There were a lot of different options for calls to make, but eventually, I decided that the best method would be to requests the data on around 350 'top artists', as defined by last.fm. This would require a two part call: one part to call the names of the top artists, and then another to request the artist information about each individual artist.

You can see the documentation here <a href="https://www.last.fm/api" target="_blank">last.fm API</a>.

I used the "chart.getTopArtists", and then "artist.getInfo".

### Step 2: Getting the Data

The next step was actually writing a call that could get me the data that I needed. The "chart.getTopArtists" was limited to fifty artists at a time, so I made seven calls to the API, extracted the names and appended all 350 of them into one list. Then, using the list I just created, I made a massive call to the "artist.getInfo" method and filled a list with all the artist info, which included listeners, playcount, genre, and more.

### Step 3: Cleaning the Data

At this point, I had the data, but I just had to organize and clean it. This ended up being a lengthy process. The data was structured in an intricate, multi-layered tangle that required extensive testing and exploration in order to understand. Each artists info was contained inside a dictionary, which contained another dictionary, which contained a list of dictionaries, which contained more dictionaries (that's not even an exaggeration). With the help of for loops and list comprehensions, I eventually managed to get the majority of it into a data frame.

One aspect that was particularly tricky though, was genre. Since each artist had between 3-6 different genres attached to their name, I had to choose how I wanted to structure it in the final data frame. There were also dozens of genres that were obscure or rare that I didn't want to use. Lastly the genres all had different spellings, so one artist might be 'hip hop', while another one was 'Hip-hop'. Eventaully though, I was able to solve these problems and create three columns so that each artist had three genres associated with them.

Unfortunately, the last.fm API was missing two pieces of information that I felt would be very useful for analysis: sex, and age. I ended up using wikipedia to get this information manually, which took a couple of hours.

### Ethical Considerations, Conclusion, Link

Fortunately for this project, I mainly used an API that was freely available to the public, so there are no ethical worries in using this data.

In conclusion, it was a challenging process that required some creativity to wrangle the data into a usable form. It was gratifying to see the completed data frame at the end though.

Here is a link to the GitHub repository. The code for reading in and wrangling the data is under 'Semester Project.ipynb', the data is found in 'artists.csv'.

<a href="https://github.com/fong31h/Stat386_Final_Project" target="_blank">Musical Artists Final Project</a>