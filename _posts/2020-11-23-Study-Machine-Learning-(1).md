---
title: "Machine Learning Study (1)"
date: 2020-11-23 16:50:28 -0400
categories: Study MachineLearning AI DeepLearning
---

## Chap1. About Artificial Intelligence
### 0. The Relationship Between Artificial Intelligence and Machine Learning and Deep Learning
&nbsp;&nbsp;&nbsp;&nbsp;Artificial intelligence, machine learning, and deep learning are used a lot, but they are often used inaccurately and their boundaries are blurred. So before I start, I would like to briefly explore their relationship. It's hard to understand the concepts from the beginning, so I hope you remember this picture first.
<pic>

### 1. What is Artificial Intelligence?
&nbsp;&nbsp;&nbsp;&nbsp;AI: A system or a program for creating human intelligence  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Strong AI: Artificial intelligence with strong performance that is no different from a person's ability.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;It cannot be made yet  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) 'Jarvis' from 'Iron Man'  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Weak AI: Artificial intelligence that performs operations in specific areas  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) driving assistance system, 'Siri' from 'Apple'

### 2. What is Machine Learning?
&nbsp;&nbsp;&nbsp;&nbsp;Machine learning modifies rules by itself.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Terminology  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Training: the computer finds its own rules of data.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Training data: data used to train models  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Model: programs created through training  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Input: the kind of problem that the model should solve  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Target: the answer that the model should match  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Supervised Learning: Use training data with targets  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Unsupervised Learning: Use training data without targets  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) clustering  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Reinforcement Learning  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;train agents with machine learning algorithms  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;trained agents perform actions optimized for a particular environment and receive rewards and current status  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;agent's goal: to be rewarded as much as possible  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;algorithms: Q-learning, SARSA, DQN  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ex) AlphaGo, DeepMind  

### 3. What is Deep Learning?
딥러닝: 복잡한 문제를 해결하기 위해 인공신경망을 다양하게 쌓은 것
머신러닝: 로지스틱 회귀, 선형 회귀, 등등등, 인공신경망 포함
인공신경망을 여러 겹으로 쌓은 모습에서 용어 유래
그래서 인공신경망과 딥러닝의 용어 구분은 거의 안한다
입력을 받아 출력으로 전달하는 뇌의 뉴런과 비슷해보이지만 딥러닝은 실제 뇌가 작동하는 방식과 다름
딥러닝은 머신 러닝이 처리하기 어려운 데이터를 더 잘 처리합니다
머신러닝: 정형데이터 (데이터베이스, 레코드 파일, 엑셀, csv)
딥러닝: 인지와 관련된 비정형 데이터(이미지, 영상, 음성, 소리, 텍스트, 번역)

#### I Referred to "정직하게 코딩하며 배우는 딥러닝 입문".
#### If you have questions, you can leave a reply on this post.
