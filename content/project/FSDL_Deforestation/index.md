---
title: "Detecting Deforestation from Satellite Images"
subtitle: Deep Learning
layout: post
date: 2020-07-30 12:38:00 -0700

draft: false
featured: false

tags:
  - Deep Learning
  - Computer Vision
  - FastAI
  - StreamLit
  - Data FlyWheel
  - Out of Domain Shift Analysis
  - Google BigQuery
  - ResNet
  - Deployment
  - MLOps
  
  
external_link: 

image:
  filename: featured.gif
  focal_point: Smart
  preview_only: false
 
  
links:
  - icon_pack: fab
    icon: github
    name: View Code/Project 
    url: 'https://github.com/karthikraja95/fsdl_deforestation_detection'
 
---

## Project Description

A Deep Learning approach to detecting deforestation risk, using satellite images and a deep learning model. We relied on Planet imagery from two Kaggle datasets (one from the Amazon rainforest and another on oil palm plantations in Borneo) and trained a ResNet model using FastAI.

## Task and Results

- Trained a ResNet50 model on [FastAI](https://docs.fast.ai/), achieving 95.6% validation accuracy and results comparable to a Kaggle competition's top of the leaderboard.
- Developed and deployed a dashboard using [Streamlit](https://streamlit.io/), which enables not only for interacting with our datasets and modeling results but also to test new images.
- Set up a data infrastructure in [Google Cloud](https://cloud.google.com/), where we stored our labels, images and data collected from users.
- Analyzed our model’s performance on out-of-domain data.
- Structured and maintained our group's project management through a [Notion](https://www.notion.so/) [workspace](https://andrecnf.com/Homepage-2ff744c443814f459d80a6e5819226a5).
- Published a [Medium article](https://andrecnf.com/Detecting-deforestation-from-satellite-images-3c83ad19879f4a0790efed8761f3c106) on [Towards Data Science](http://towardsdatascience.com/).
- Got the web app featured at the top of [Streamlit's official weekly roundup](https://discuss.streamlit.io/t/weekly-roundup-rasalit-deforestation-detection-api-creators-and-more/13115).
- Highlighted on [PyCoders weekly newsletter](https://pycoders.com/issues/475).

## Links

[Full Stack Deep Learning - Final Project Submission](https://github.com/karthikraja95/fsdl_deforestation_detection)

[Short Video](https://www.loom.com/share/365d412db3a0474ba46d4fdd7f4c5494)

[Detailed Report](https://towardsdatascience.com/detecting-deforestation-from-satellite-images-7aa6dfbd9f61)
