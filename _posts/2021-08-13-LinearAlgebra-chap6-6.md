---
layout: post
title: "6.6 베이즈 정리"
date: 2021-08-13 15:56:28 -0400
categories: [선형대수학]
tags: [선형대수학]
comments: true
math: true
---

## 베이즈 정리
- 데이터 조건이 주어졌을 대의 조건부확률을 구하는 공식
- 데이터의 사전확률값이 주어지면 새로운 데이터와 합쳐서 변화에 대해 계산할 수 있음
- 새로운  데이터가 들어왓을 때 이전 데이터에 대한 분석을 할 필요 없음
- $$P(A|B) = {P(B|A)P(A) \over P(B)}$$
    - $$P(A)$$: 사전확률(prior)
    - $$P(A|B)$$: 사후확률(posterior)
    - $$P(B|A)$$: 가능도(likelihood)
    - $$P(B)$$: 정규화 상수(normalizing constant, evidence)

## 베이즈 정리의 확장 1
- 멀티-클래스 분류 문제에 활용
- $$A_i \cap A_j = \emptyset$$ 이고 $$A_1 \cup A_2 \cup \cdots = \Omega$$이면
- $$P(A_i|B) = {P(B|A_i)P(A_i) \over P(B)} = {P(B|A_i)P(A_i) \over \sum_j P(A_j, B)} = {P(B|A_i)P(A_i) \over \sum_j P(B|A_j)P(A_j)}$$
- $$P(A_i|B) \propto P(B|A_i)P(A_1)$$

## 검사 시약 문제
- D: 병에 걸리는 경우
- S: 양성 반응을 보이는 경우
- $$P(S|D) = 0.99, P(D) = 0.002, P(S|D^C) = 0.05$$ 라면
- $$P(D|S) = {P(S|D)P(D) \over P(S)} = {P(S|D)P(D) \over P(S,D)+P(S,D^C)} = {P(S|D)P(D) \over P(S|D)P(D)+P(S|D^C)(1-P(D))} = 0.038$$

## 베이즈 정리의 확장 2
- $$P(A|B,C) = {P(C|A,B)P(A|B) \over P(C|B)}$$

## 몬티 홀 문제
- 세 개의 문 중에 하나를 선택하여 문 뒤에 있는 선물을 가지는 게임쇼에 참가했다. 한 문 뒤에는 자동차가 있고, 나머지 두 문 뒤에는 염소가 있다. 이때 어떤 사람이 예를 들어 1번 문을 선택했을 때, 게임쇼 진행자는 3번 문을 열어 문뒤에 염소가 있음을 보여주면서 1번 대신 2번을 선택하겠냐고 물었다. 참가자가 자동차를 가지려할 때 원래 선택했던 번호를 바꾸는 것이 유리할까?
- $$C$$: 자동차가 있는 문을 나타내는 확률변수
- $$X$$: 참가자가 선택한 문을 나타내는 확률변수
- $$H$$: 진행자가 열어준 문을 나타내는 확률변수
1. $$P(C,X) = P(C)P(X)$$ (참가자와 진행자는 서로의 선택에 대해 알지 못하므로)
2. 참가자가 1번 문을 선택했을 때
    1. 자동차가 0번 문 뒤에 있다면 진행자는 2번 문을 열 수 밖에 없다.
        - $$P(H_0|C_0, X_1) = 0$$
        - $$P(H_1|C_0, X_1) = 0$$
        - $$P(H_2|C_0, X_1) = 1$$
    2. 자동차가 1번 문 뒤에 있다면 진행자는 0번 문과 2번 문 둘다 열 수 있다.    
        - $$P(H_0|C_1, X_1) = {1 \over 2}$$
        - $$P(H_1|C_1, X_1) = 0$$
        - $$P(H_2|C_1, X_1) = {1 \over 2}$$
3. 이 상황에 진행자가 2번 문을 열어서 자동차가 없다는 것을 보인 경우
    - $$P(C_0|X_1, H_2) = {P(C_0, X_1, H_2) \over P(X_1, H_2)}$$<br/>
    $$= {P(H_2|C_0, X_1)P(C_0, X_1) \over P(X_1, H_2)} = {P(C_0)P(X_1) \over P(H_2|X_1)P(X_1)}$$<br/> 
    $$= {P(C_0) \over P(H_2|X_1)} = {2 \over 3}$$
    - $$P(C_1|X_1, H_2) = 1 - P(C_0|X_1, H_2) = {1 \over 3}$$ (이진 분류 문제이므로)
4. 참가자는 선택을 바꾸는 것이 유리하다.

## 연습문제
- 6.6.1
    - $$P(A \vert B,C) = {P(A \cap B \cap C) \over P(B,C)} = {P(B \cap (A \cap C)) \over P(B,C)} = {P(B \vert A,C)P(A,C) \over P(B,C)}$$<br/>
    $$= {P(B \vert A,C)P(A \vert C)P(C) \over P(B \vert C)P(C)} = {P(B \vert A,C)P(A \vert C) \over P(B \vert C)}$$
- 6.6.2
    - $$P(A \vert B,C,D) = {P(A,B,C,D) \over P(B,C,D)} = {P(D \vert A,B,C)P(A,B,C) \over P(D \vert B,C)P(B,C)}$$<br/>
    $$= {P(D \vert A,B,C)P(A \vert B,C)P(B,C) \over P(D \vert B,C)P(B,C)} = {P(D \vert A,B,C) P(A \vert B,C) \over P(D \vert B,C)}$$
- 6.6.3
    - $$P(A,B \vert C,D) = {P(A,B,C,D) \over P(C,D)} = {P(D \vert A,B,C)P(A,B,C) \over P(D \vert C)P(C)}$$<br/>
    $$= {P(D \vert A,B,C)P(A,B \vert C)P(C) \over P(D\vert C)P(C)} = {P(D \vert A,B,C)P(A,B \vert C) \over P(D \vert C)}$$

<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.