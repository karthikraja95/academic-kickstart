---
title: "Music Generation"
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
  - RNN
  
  
external_link: 

image:
  filename: featured.png
  focal_point: Smart
  preview_only: false
  #caption: 
  
links:
  - icon_pack: fab
    icon: github
    name: View Code/Project 
    url: 'https://github.com/karthikraja95/Music_Generation'
 
---


Multi-layer recurrent neural networks for training and sampling from texts, inspired by [karpathy/char-rnn](https://github.com/karpathy/char-rnn).

### Requirements

This code is written in Python 2, and it requires the [Keras](https://keras.io) deep learning library.

### Usage

All input data should be placed in the `data/` directory. The example `input.txt` is taken from the [Nottingham Dataset (Cleaned)](https://github.com/jukedeck/nottingham-dataset).

To train the model with default settings:
```bash
$ python train.py
```

To sample the model:
```bash
$ python sample.py 100
```

Training loss/accuracy is stored in `logs/training_log.csv`.
