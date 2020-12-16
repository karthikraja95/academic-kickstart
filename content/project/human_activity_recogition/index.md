---
title: "Human Activity Recognition"
subtitle: Deep Learning
layout: post
date: 2020-07-30 12:38:00 -0700

draft: false
featured: false

tags:

  - Deep Learning
  - Python
  - Keras
  - LSTM
  - NLP
  
  
  
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
    url: 'https://github.com/karthikraja95/HumanActivityRecognition'
 
---

This project is to build a model that predicts the human activities such as Walking, Walking_Upstairs, Walking_Downstairs, Sitting, Standing or Laying.

This dataset is collected from 30 persons(referred as subjects in this dataset), performing different activities with a smartphone to their waists. The data is recorded with the help of sensors (accelerometer and Gyroscope) in that smartphone. This experiment was video recorded to label the data manually.

## Data

All the data is present in 'UCI_HAR_dataset/' folder in present working directory.
Feature names are present in 'UCI_HAR_dataset/features.txt'

1.Train Data:

1. 'UCI_HAR_dataset/train/X_train.txt'
2. 'UCI_HAR_dataset/train/subject_train.txt'
3. 'UCI_HAR_dataset/train/y_train.txt'

2.Test Data:

1. 'UCI_HAR_dataset/test/X_test.txt'
2. 'UCI_HAR_dataset/test/subject_test.txt'
3. 'UCI_HAR_dataset/test/y_test.txt'


## Qucik overview of the dataset:

1. Accelerometer and Gyroscope readings are taken from 30 volunteers(referred as subjects) while performing the following 6 Activities.
Walking
WalkingUpstairs
WalkingDownstairs
Standing
Sitting
Lying.
2. Readings are divided into a window of 2.56 seconds with 50% overlapping.
3. Accelerometer readings are divided into gravity acceleration and body acceleration readings, which has x,y and z components each.
4. Gyroscope readings are the measure of angular velocities which has x,y and z components.
5. Jerk signals are calculated for BodyAcceleration readings.
6. Fourier Transforms are made on the above time readings to obtain frequency readings.
7. Now, on all the base signal readings., mean, max, mad, sma, arcoefficient, engerybands,entropy etc., are calculated for each window.
8. We get a feature vector of 561 features and these features are given in the dataset.
9. Each window of readings is a datapoint of 561 features.

## Problem Framework

1. 30 subjects(volunteers) data is randomly split to 70%(21) test and 30%(7) train data.
2. Each datapoint corresponds one of the 6 Activities.

## Problem Statement

1. Given a new datapoint we have to predict the Activity
