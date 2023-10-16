---
layout: post
title:  "How To Set Up and Understand a (Very) Simple Neural Network"
author: Spencer Fong
description: An easy to understand how-to for someone who's curious about neural networks
image: "/assets/images/nn.png"
---
## How to Understand and Set Up a Basic Neural Network

# Intro

Like the rest of the world, I noticed a large uptake in discourse and media attention surrounding artificial intelligence after the free release of ChatGPT 3 in November 2022. As a university student studying statistics and data science, I’ve always vaguely understood that AI is connected to the field I am training in, but never understood how, or why. That’s why I chose to research this topic for my first blog post about data science. I ended up choosing to write specifically about neural networks, since that is a term I had heard before and wondered about, and is also the basis for popular generative AI like ChatGPT.
In this blog post, I’m going to dive into the topic, break it down very simply, and include instructions for visualizing these concepts in the programming language Python.

# A Bit of Background

To get a handle on what a neural network is, the first thing that you have to understand is the term artificial intelligence. In short, artificial intelligence is a field that aims to build machines that mimic human behavior. Within the field of artificial intelligence, is a sub-field called machine learning. Machine learning is a method of using computers to find patterns in data. Within machine learning, there is another sub-field called deep learning. Deep learning is a very specific type of machine learning, which uses a set up called a neural network. Neural networks are meant to imitate the structure of the human brain. The function of deep learning is the same as machine learning, to find patterns in data. Deep learning uses neural networks because it is a powerful set up that is capable of impressive performance in pattern recognition.

# Neural Networks in Plain English

Neural networks are basically made up of two things, neurons, and channels. Neurons sit in columns and are connected to each other by channels (see header image). Neurons take in information that is passed through the channels and decide, based on that information, whether to activate. At the end, an output is selected based on which neurons activated. Neurons decide whether to activate based on three things: the input, the weight of the channel, and the bias of the neuron.

These concepts will be explained more in the Python example. For now, it’s helpful to visualize a specific scenario. Imagine you passed in a picture of a cat to a neural network. This picture is the input. The goal is for the network to identify what animal it is. What a neural network will do, is break the input apart, and send its contents through channels, to each neuron. The weights of the channels decide which pieces of input the neuron receives. So, for example, one neuron might only receive input about the top left corner of the picture. This is achieved by applying a weight of zero to all parts of the input not coming from the top left corner. Then, each neuron will add up its information and if the total is higher than the bias (think of the bias a threshold that needs to be reached), the neuron will activate and pass its information on. To decide the output, the network compares the totaled-up information from all neurons that activated to see which animal that information most closely corresponds to. For example, maybe a total of 32.34 is recorded and in the list of possible outputs, the network has ‘dog’, at 32, ‘cat’ at 32.5, and ‘bear’ at 33. The network would then select ‘cat’ as the output as it is closest.

Choosing proper weights, biases, and output values is near impossible to do by hand for any real-world application. Luckily, there are complicated processes (involving lots of math) that can be used to train neural networks to adjust these values until they achieve correct outcomes.

# A Python Example

Okay, so now that we understand what a neural network is basically doing, let’s solidify that knowledge with a little example. The Python used in this example is basic, although you will have to understand what a class is and how they function.

First, let’s pretend that you can represent an animal using three numbers, between 0 and 1. The first number represents the legs, the second number represents the ears, and the last number represents the tail. We are going to pass a list of these three numbers into our neural network we create and see if it decides that the list represents a cat, a dog, or neither.

 {% raw %}![Figure]({{site.url}}/{{site.baseurl}}/assets/images/pic 1.png){% endraw %}
