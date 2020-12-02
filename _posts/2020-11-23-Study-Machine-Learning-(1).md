---
title: "Machine Learning Study (1)"
date: 2020-11-23 16:50:28 -0400
categories: Study MachineLearning AI DeepLearning
---

## Chap1. About Artificial Intelligence
### 0. The Relationship Between Artificial Intelligence and Machine Learning and Deep Learning
&nbsp;&nbsp;&nbsp;&nbsp;Artificial intelligence, machine learning, and deep learning are used a lot, but they are often used inaccurately and their boundaries are blurred. So before I start, I would like to briefly explore their relationship. It's hard to understand the concepts from the beginning, so I hope you remember this picture first.

### 1. What is Artificial Intelligence?
&nbsp;&nbsp;&nbsp;&nbsp;Artificial intelligence (AI) is a system or program to mimic human intelligence. And AI is divided into strong AI and weak AI.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Strong AI: Artificial intelligence with strong performance that is no different from a person's ability.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It cannot be made yet  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) "Jarvis" from "Iron Man"  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Weak AI: Artificial intelligence that performs operations in specific areas  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) driving assistance system, "Siri" from 'Apple'

### 2. What is Machine Learning?
&nbsp;&nbsp;&nbsp;&nbsp;Machine learning requires humans to process data first, machines learn it themselves. And machine learning models modify rules by itself.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Terminology  
```
Training: a process that a computer finds rules for data.
Training data: data used to train models  
Model: programs created through training  
Input: this is a problem that the model has to solve, and most of the time, it is data.  
Target: the answer that the model should find out  
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Supervised Learning: Use training data with targets, i.e. data with correct answers.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) Classification, Regression
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Unsupervised Learning: Use training data without targets, which means that the model makes the correct answer on its own.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) clustering  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Reinforcement Learning
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;train agents with machine learning algorithms  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;trained agents perform actions optimized for a particular environment and receive rewards and current status  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;agent's goal: to be rewarded as much as possible  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;algorithms: Q-learning, SARSA, DQN  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) AlphaGo, DeepMind  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Rules: It refers to weight and intercept
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;;&nbsp;&nbsp;&nbsp;&nbsp;Most machine learning algorithms can mathematically express the relationship between training data and rules. And if the predicted and actual target values do not match, the rules in the model must be modified.The model modifies the rules according to the loss function to be detailed later. So learning is done by finding the highest value of the loss function.
```
ex) 1.5x + 0.1 = y
x: input
y: target
1.5: weight
0.1: intercept
(weight and intercept are model parameters)
```

### 3. What is Deep Learning?
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Deep learning
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Deep learning is an artificial neural network to solve complex problems without data processing by humans. The term Deep Learning derives from the appearance of multiple layers of artificial neural networks. It is called mixed with artificial neural network and deep learning, but hardly distinguishes terms. Deep learning looks like a neuron in the brain that receives input and transmits it to the output, but deep learning is different from how the actual brain works. And deep learning handles data that is difficult for machine learning to process better.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Machine learning: More suitable for structured data such as database, record file, Excel, and csv.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Deep Learning: More suitable for unstructured data related to recognition, such as images, images, voices, sounds, text, translations, etc.

#### Referred to "정직하게 코딩하며 배우는 딥러닝 입문".
#### If you have questions, you can leave a reply on this post.
