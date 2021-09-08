---
layout: post
title: "6.2 확률의 수학적 정의와 의미"
date: 2021-08-10 14:07:28 -0400
categories: [데이터 사이언스 수학]
tags: [선형대수학]
comments: true
math: true
---

## 표본공간과 확률표본
- 표본공간(sample space)
    - 가능한 모든 확률표본의 집합 ($$\Omega$$) 
- 확률표본(probabilistic sample, random sample)
    - 풀고자 하는 확률적 문제에서 발생할 수 있는 하나의 현상
    - 선택될 수 있는 하나의 경우
    - = 표본(sample)

- 집합(set): 구별 가능한 객체의 모임 (보통 알파벳 대문자로 표기)
- 원소(element): 집합에 포함된 구별 가능한 객체 (보통 알파벳 소문자로 표기)
- 예시
    - $$x \in A$$
    - $$x \notin A$$
    - $$A = \{1, 2, 3\} \rightarrow 1 \in A, 4 \notin A$$ 

## 사건
- 사건
    - 표본공간의 부분집합
    - 보통 알파벳 대문자로 표기

## 확률
- 확률(P): 사건을 입력했을 때 확률값이 출력되는 함수
- 정의역(domain): 표본공간의 모든 사건의 집합
- 규칙(Kolmogorov's axioms)
    - $$P(A) \geq 0$$
    - $$P(\Omega) = 1$$
    - $$A \cap B = \emptyset \rightarrow P(A \cup B) = P(A) + P(B)$$

## 확률은 표본이 아닌 사건을 입력으로 가지는 함수
- 오류: 확률이 표본 하나 하나에 대해 정의되 있는 숫자 ($$P(1) = {1 \over 6}$$)
- 확률은 표본이 아닌 사건에 대해 정의한다 ($$P(\{1\}) = {1 \over 6}$$)

## 주사위 한 면의 확률은 무조건 1/6?
- 콜모코로프의 공리를 따른다면 주사위에 어떤 조작이든 가능하기 때문에 항상 그렇지는 않다.

## 확률의 의미
- 빈도주의(Frequentist)
    - 사건의 확률: 반복적으로 선택된 표본이 사건의 원소가 될 경향 
- 베이지안(Bayesian)
    - 확률: 선택된 표본이 특정한 사건에 속한다는 가설, 명제, 혹은 주장의 신뢰도(반복이라는 개념을 사용되지 않음)

## 연습문제
- 6.2.1<br/>
    1. $$\Omega_3 = \{HH, HT, TH, TT\}$$
    2. $$\Omega_4 = \{1, 2, \cdots, 30, 31 \}$$
- 6.2.2
    - $$\Omega_7 = \{ x: 0 \leq x \leq 359 \}$$
    - 표본 개수는 무한대이다.
- 6.2.3
    - 동전을 던졌을 때 나오는 면
    - 10개의 돌을 무작위로 잡았을 때 잡힌 돌의 갯수
    - 1과 2 사이의 무작위로 고른 실수
    - 펜을 돌렸을 때 시작점과 이루는 각도
- 6.2.4
    1. 
        ```python
        A = frozenset(['H'])
        B = frozenset(['T'])
        set([A, B])
        ```
    2.  
        ```python
        A = frozenset(['HH'])
        B = frozenset(['HT'])
        C = frozenset(['TH'])
        D = frozenset(['TT'])
        set([A, B, C, D])
        ```
- 6.2.5
    1. ```python
        P = {A: 0.5, B: 0.5}
        P
        
        >>>
        {frozenset(): 0.5,
         frozenset({'H'}): 0.5}
        ```
    2. ```python
        P = {A: 0.25, B: 0.25, C: 0.25, D: 0.25}
        P
        
        >>>
        {frozenset('HH'): 0.25,
         frozenset({'HT'}): 0.25,
         frozenset({'TH'}): 0.25,
         frozenset({'TT'}): 0.25}}
        ```
- 6.2.6
    -  ```python
        A = frozenset(['1'])
        B = frozenset(['2'])
        C = frozenset(['3'])
        D = frozenset(['4'])
        E = frozenset(['5'])
        F = frozenset(['6'])
        set([A, B, C, D, E, F])
        
        P = {A: 0.5, B: 0.2, C: 0.1, D: 0.1, E: 0.1, F: 0}
        print(P)
            
        >>>
        {frozenset({'1'}): 0.5, frozenset({'2'}): 0.2, frozenset({'3'}): 0.1, frozenset({'4'}): 0.1, frozenset({'5'}): 0.1, frozenset({'6'}): 0}
       ```
- 6.2.7
    1. $$P(A) = {P(\{31\}) \over P(\Omega)} = {1 \over 31}$$
    2. $$P(\{A\}) = {P(\{A\}) \over P(\Omega)}, P(\{O\}) = {P(\{O\}) \over P(\Omega)}$$
    3. $$P(\{A\}) = {70 \over 100}, P(\{O\}) = {30 \over 100}$$


<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.