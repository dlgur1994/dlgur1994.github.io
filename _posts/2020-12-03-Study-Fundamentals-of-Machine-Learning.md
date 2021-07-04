---
title: "Fundamentals of Machine Learning"
date: 2020-12-04 15:50:28 -0400
categories: Study AI MachineLearning DeepLearning
---

### 1. 데이터
표에서 row는 sample, column은 feature (independent variable, explanatory variable)이다.
DATA_NAME.data 로 feature 접근, DATA_NAME.target 으로 sample 접근

### 2. 선형 회귀
선형 회귀는 기울기와 절편을 찾아낸다. 기울기와 절편이 잘 만들어졌다면 이는 선형 회귀로 만든 모델이 된다.
  y = ax + b
  a: slope
  b: intercept

  y^ = wx + b
  w: weight
  b: intercept
<br/>

### 3. 경사 하강법
  w와 b를 찾는법
  1. 무작위로 w와 b를 선택
  2. 샘플 하나를 선택하여 y^ 계산
  3. y^와 y 비교
  4. y^오 y가 더 가까워지도록 w, b 조정
  5. 모든 샘플에 대해 2~4번 반복

### 4. 역전파
  

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
_ex) classification, regression_  
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

### 3. What is Deep Learning?
Deep learning is an artificial neural network to solve complex problems without data processing by humans. The term Deep Learning derives from the appearance of multiple layers of artificial neural networks. It is called mixed with artificial neural network and deep learning, but hardly distinguishes terms. Deep learning looks like a neuron in the brain that receives input and transmits it to the output, but deep learning is different from how the actual brain works. And deep learning handles data that is difficult for machine learning to process better.  
_cf) Machine learning is more suitable for structured data such as database, record file, Excel, and csv. And deep learning is more suitable for unstructured data related to recognition, such as images, images, voices, sounds, text, translations, etc._  
<br/>

#### Referred to "정직하게 코딩하며 배우는 딥러닝 입문"<br/>If you have questions, you can leave a reply on this post.
