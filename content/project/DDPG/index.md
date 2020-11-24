---
title: "Continuous Control: Deep Deterministic Policy Gradient"
subtitle: Reinforcement Learning
layout: post
date: 2020-07-30 12:38:00 -0700

draft: false
featured: true

tags:
  - Reinforcement Learning
  - PyTorch
  - Python
  - Policy Based Methods
  - Unity ML
  - Deep Deterministic Policy Gradient (DDPG)
  
external_link: 

image:
  filename: featured.gif
  focal_point: Smart
  preview_only: false
  caption: Trained Agent using DDPG
  
links:
  - icon_pack: fab
    icon: github
    name: View Code 
    url: 'https://github.com/karthikraja95/Deep-Reinforcement-Learning-Continuous-Control'
 
---

This project repository contains my work for the Udacity's [Deep Reinforcement Learning Nanodegree](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893) Project 2: Continuous Control.

## Project's goal

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, **the goal of the agent is to maintain its position at the target location for as many time steps as possible.**

In this Project, I am training an agent to maintain its position at the target location for as many time steps as possible.


### About Deep Reinforcement Learning

> [Reinforcement learning](https://skymind.ai/wiki/deep-reinforcement-learning) refers to goal-oriented algorithms, which learn how to attain a complex objective (goal) or maximize along a particular dimension over many steps; for example, maximize the points won in a game over many moves. They can start from a blank slate, and under the right conditions they achieve superhuman performance. Like a child incentivized by spankings and candy, these algorithms are penalized when they make the wrong decisions and rewarded when they make the right ones – this is reinforcement.

In this project I have chosen to use a Policy Based method called [DDPG (Deep Deterministics Policy Gradient)](https://spinningup.openai.com/en/latest/algorithms/ddpg.html)


