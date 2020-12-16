---
title: "Facebook Social Network Graph Prediction"
subtitle: Machine Learning
layout: post
date: 2020-07-30 12:38:00 -0700

draft: false
featured: false

tags:

  - Machine Learning
  - Python
  - Feature Engineering
  - Hyperparameter Tuning
  - Random Forest
  - Visualization
  
  
  
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
    url: 'https://github.com/karthikraja95/kaggle-Facebook_Challenge'
 
---

# Social network Graph Link Prediction - Facebook Challenge

### Problem statement:

Given a directed social graph, have to predict missing links to recommend users (Link Prediction in graph)

### Data Overview

Taken data from facebook's recruting challenge on kaggle https://www.kaggle.com/c/FacebookRecruiting
data contains two columns source and destination eac edge in graph
- Data columns (total 2 columns):  
- source_node         int64  
- destination_node    int64  

### Mapping the problem into supervised learning problem:

Generated training samples of good and bad links from given directed graph and for each link got some features like no of followers, is he/she followed back, page rank, katz score, adar index, some svd fetures of adj matrix, some weight features etc. and trained ml model based on these features to predict link.

### Some reference papers and videos :

https://www.cs.cornell.edu/home/kleinber/link-pred.pdf

https://www3.nd.edu/~dial/publications/lichtenwalter2010new.pdf

https://kaggle2.blob.core.windows.net/forum-message-attachments/2594/supervised_link_prediction.pdf

https://www.youtube.com/watch?v=2M77Hgy17cg

### Business objectives and constraints:

No low-latency requirement.
Probability of prediction is useful to recommend ighest probability links

### Performance metric for supervised learning:

Both precision and recall is important so F1 score is good choice
Confusion matrix
