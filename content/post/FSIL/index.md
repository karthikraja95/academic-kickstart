---
title: "Incremental Few-Shot Learning (IFSL)"
date: 2021-01-114
math: true
diagram: true
image:
  # placement: 3
  # caption: 'Image credit: [**John Moeses Bauan**](https://unsplash.com/photos/OGZtQF8iC0g)'
---



## What is Few Shot Learning?

The human visual system exhibits the remarkable ability to effortlessly learn novel concepts from only one or a few examples and reliably recognize them later on. I think the human visual system is so efficient when learning novel concepts because it exploits its past experiences about the (visual) world. For example: As humans, we have an excellent representation of the world; we only need a few samples to identify a car or a building. Mimicking this behaviour on an Artificial Intelligence system is called Few-Shot Learning. This research area is exciting and challenging with many practical, real-world applications, including real-time vision interactive applications.

## What is Incremental Learning?

Incremental Learning refers to a family of scalable algorithms that learn to sequentially update models from infinite data streams. Whereas in “traditional” machine learning, we’re given a complete dataset consisting of (input, output) pairs, in Incremental Learning, we don’t have all of the data available when creating the model. Instead, the data points arrive one at a time, and we have to build a “living” model, one that learns and adapts as the data comes. 

*The aim of the article to understand the state of the art techniques in Incremental Few-Shot  Learning (IFSL)*


## Dynamic Few-Shot Visual Learning without Forgetting

Most prior research methods neglected two essential characteristics of few-shot learning:

- Learning of novel categories (new categories that are not available during training time) needs to be fast
- Do not sacrifice any recognition accuracy on the base categories (the initial categories the model was trained on) 


This work, Dynamic Few-Shot Visual Learning without Forgetting motivated based on the above shortcoming, developed an object recognition learning model that not only able to recognize the base categories but also dynamically learns to recognize the novel categories from only a few training samples (usually 1 to 5 ).  The authors achieved state-of-the-art results on few-shot learning by proposing :

- An Attention based few-shot classification weight generator
- Implement ConvNet classifier Model as a cosine similarity (instead of dot product) function between feature representations and classification vectors. 

## Overiew of Dynamic Few-Shot Visual Learning without Forgetting 

![Dynamic Few-Shot Visual Learning without Forgetting](Dynamic-Few-Shot.PNG)

> Overview of our system. It consists of: (a) a ConvNet based recognition model (that includes a feature extractor and a classifier)
and (b) a few-shot classification weight generator. Both are trained on a set of base categories for which we have available a large set of
training data. During test time, the weight generator gets as input a few training data of a novel category and the classification weight
vectors of base categories (green rectangle inside the classifier box) and generates a classification weight vector for this novel category (blue
rectangle inside the classifier box). This allows the ConvNet to recognize both base and novel categories.

## Observations:

- Few-Shot Learning is not feasible with a typical dot-product-based Classifier because we need to train both base and novel categories separately. On the other hand, Cosine-Similarity based Classifier unified the learning process of both base and novel categories.
- Cosine-Similarity based Classifier leads the feature extractor to learn features that generalize significantly better on novel categories than features learned with the dot-product based Classifier.
- Thanks to the Cosine-Similarity based Classifier, the base classification weight vectors learn to be representative feature vectors of their categories. Thus, the base classification weight vectors also encode visual similarity. 
- Using an attention-based weight composition, the classification weight vector of a novel category can be composed as a linear combination of those base classification weight vectors that are most similar to the few training examples of that category. Attention-based weight composition allows our few-shot weight generator to explicitly exploit the acquired knowledge about the visual word (here represented by the base classification weight vectors) to improve the few-shot recognition performance. 


Refer to [Dynamic Few-Shot Visual Learning without Forgetting](https://arxiv.org/pdf/1804.09458.pdf) for detailed methodology, results and comparisons.


## Incremental Few-Shot Learning with Attention Attractor Networks 


The authors presented a novel method for incremental few-shot learning where during meta-learning, the authors optimized a regularizer that reduces catastrophic forgetting from the incremental few-shot learning. The proposed regularizer is inspired by [attractor networks](http://proceedings.mlr.press/v80/liao18c/liao18c.pdf) and can be thought of as a memory of the base classes, adapted to the new classes. They also showed how this regularizer could be optimized, using [recurrent back-propagation](https://home.cs.colorado.edu/~mozer/Research/Selected%20Publications/reprints/ZemelMozer2001.pdf) to back-propagate through the few-shot optimization stage. During each few-shot episode, we directly learn a classifier network that is randomly initialized and solved till convergence, unlike Dynamic Few-Shot Visual Learning without Forgetting which directly outputs the prediction. 

## Architecture Overview

![Incremental Few-Shot Learning with Attention Attractor Networks ](Attention_Attractor_Networks.PNG)

> The proposed attention attractor network for incremental few-shot learning. During
pretraining we learn the base class weights Wa and the feature extractor CNN backbone. In the
meta-learning stage, a few-shot episode is presented. The support set only contains novel classes,
whereas the query set contains both base and novel classes. We learn an episodic classifier network
through an iterative solver, to minimize cross entropy plus an additional regularization term predicted
by the attention attractor network by attending to the base classes. The attention attractor network is
meta-learned to minimize the expected query loss. During testing an episodic classifier is learned in
the same way.

Incremental Few-Shot Learning with Attention Attractor Networks has several stages: 

- **Pre-training stage**: We learn a base model for the regular supervised classification task on the dataset. The purpose of this stage is to learn both a good base classifier and a good representation. The parameters of the base classifier are learned in this stage and will be fixed after pre-training.

- **Incremental Few-Short Episodes**: A few-shot dataset can be the same data source as the pre-training dataset but sampled episodically from which we can sample few-shot learning episodes. In each episode, we learn a classifier on the support set whose learnable parameters are called the fast weights, as they are only used during this episode.

- **Metra-Learning Stage**: The authors iteratively sample few-shot episodes and learn the meta-parameters to minimize the joint prediction loss*. In particular, we design a regularizer* using Attention Attractor Networks such that the fast weights are learned via minimizing the loss, which typically a cross-entropy loss for a few-shot classification.

* *Join Prediction Loss and Attention Attractore Networks Regularizer details are explained clearly in the paper. *

