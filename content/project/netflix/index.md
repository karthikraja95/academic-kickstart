---
title: "Netflix Movie Recommendation System"
subtitle: Machine Learning
layout: post
date: 2020-07-30 12:38:00 -0700

draft: false
featured: false

tags:
  
  - Machine Learning
  - Python
  - SQL
  - Feature Engineering
  - Collaborative Filtering
  - Ensemble Methods
  - SVD
  - Recommendation System
  
  
external_link: 

image:
  filename: featured.png
  focal_point: Smart
  preview_only: false
  #caption: Reinforcement Learning Agents
  
links:
  - icon_pack: fab
    icon: github
    name: View Code/Project 
    url: 'https://github.com/karthikraja95/NetflixMovieRecommender'
 
---

## Problem Description

Netflix is all about connecting people to the movies they love. To help customers find those movies, they developed world-class movie recommendation system: CinematchSM. Its job is to predict whether someone will enjoy a movie based on how much they liked or disliked other movies. Netflix use those predictions to make personal movie recommendations based on each customer’s unique tastes. And while Cinematch is doing pretty well, it can always be made better.

Now there are a lot of interesting alternative approaches to how Cinematch works that netflix haven’t tried. Some are described in the literature, some aren’t. We’re curious whether any of these can beat Cinematch by making better predictions. Because, frankly, if there is a much better approach it could make a big difference to our customers and our business.

Credits: https://www.netflixprize.com/rules.html

## Problem Statement

Netflix provided a lot of anonymous rating data, and a prediction accuracy bar that is 10% better than what Cinematch can do on the same training data set. (Accuracy is a measurement of how closely predicted ratings of movies match subsequent actual ratings.)

## Sources

1. https://www.netflixprize.com/rules.html
2. https://www.kaggle.com/netflix-inc/netflix-prize-data
3. Netflix blog: https://medium.com/netflix-techblog/netflix-recommendations-beyond-the-5-stars-part-1-55838468f429 (very nice blog)
4. surprise library: http://surpriselib.com/ (we use many models from this library)
5. surprise library doc: http://surprise.readthedocs.io/en/stable/getting_started.html (we use many models from this library)
6. installing surprise: https://github.com/NicolasHug/Surprise#installation
7. Research paper: http://courses.ischool.berkeley.edu/i290-dm/s11/SECURE/a1-koren.pdf (most of our work was inspired by this paper)
8. SVD Decomposition : https://www.youtube.com/watch?v=P5mlg91as1c

## Business Objectives

### Objectives:
1. Predict the rating that a user would give to a movie that he ahs not yet rated.
2. Minimize the difference between predicted and actual rating (RMSE and MAPE)
### Constraints:
1. Some form of interpretability.

## Machine Learning Problem

For a given movie and user we need to predict the rating would be given by him/her to the movie. The given problem is a Recommendation problem . It can also seen as a Regression problem 

## Performance Metric

1. Mean Absolute Percentage Error: https://en.wikipedia.org/wiki/Mean_absolute_percentage_error
2. Root Mean Square Error: https://en.wikipedia.org/wiki/Root-mean-square_deviation



