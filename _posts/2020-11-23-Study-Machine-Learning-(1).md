---
title: "Machine Learning Study (1)"
date: 2020-11-23 16:50:28 -0400
categories: Study MachineLearning AI DeepLearning
---

## Chap1. About Artificial Intelligence
### 0. The Relationship Between Artificial Intelligence and Machine Learning and Deep Learning
Artificial intelligence, machine learning, and deep learning are used a lot, but they are often used inaccurately and their boundaries are blurred. So before I start, I would like to briefly explore their relationship. It's hard to understand the concepts from the beginning, so I hope you remember this picture first.  
![capture1](https://user-images.githubusercontent.com/38805855/100973006-2271ce80-357d-11eb-943d-4a848cb4ec92.PNG){: width="30%" height="30%"}
<br/>

### 1. What is Artificial Intelligence?
Artificial intelligence (AI) is a system or program to mimic human intelligence. And AI is divided into strong AI and weak AI.  
Strong AI: Artificial intelligence with strong performance that is no different from a person's ability, but it cannot be made yet.
_ex) "Jarvis" from "Iron Man"_  
Weak AI: Artificial intelligence that performs operations in specific areas
_ex) driving assistance system, "Siri" from 'Apple'_  
<br/>

### 2. What is Machine Learning?
Machine learning requires humans to process data first, machines learn it themselves. And machine learning models modify rules by itself.  
Training: a process that a computer finds rules for data.  
Training data: data used to train models  
Model: programs created through training  
Input: this is a problem that the model has to solve, and most of the time, it is data.  
Target: the answer that the model should find out  
Supervised Learning: It uses training data with targets, i.e. data with correct answers.  
_ex) Classification, Regression_  
Unsupervised Learning: It uses training data without targets, which means that the model makes the correct answer on its own.  
_ex) clustering_  
Reinforcement Learning: It trains agents with machine learning algorithms. The trained agents perform actions optimized for a particular environment and receive rewards and current status. The agent's goal is to be rewarded as much as possible  
_algorithms: Q-learning, SARSA, DQN_  
_ex) "AlphaGo", "DeepMind"_  
Rules: It refers to weight and intercept  
Most machine learning algorithms can mathematically express the relationship between training data and rules. And if the predicted and actual target values do not match, the rules in the model must be modified.The model modifies the rules according to the loss function to be detailed later. So learning is done by finding the highest value of the loss function.
```
ex) 1.5x + 0.1 = y
    x: input
    y: target
    1.5: weight
    0.1: intercept
    (weight and intercept are model parameters)
```
<br/>

### 3. What is Deep Learning?
Deep learning is an artificial neural network to solve complex problems without data processing by humans. The term Deep Learning derives from the appearance of multiple layers of artificial neural networks. It is called mixed with artificial neural network and deep learning, but hardly distinguishes terms. Deep learning looks like a neuron in the brain that receives input and transmits it to the output, but deep learning is different from how the actual brain works. And deep learning handles data that is difficult for machine learning to process better.  
_cf) Machine learning is more suitable for structured data such as database, record file, Excel, and csv. And deep learning is more suitable for unstructured data related to recognition, such as images, images, voices, sounds, text, translations, etc._  
<br/>

#### Referred to "정직하게 코딩하며 배우는 딥러닝 입문"<br/>If you have questions, you can leave a reply on this post.
