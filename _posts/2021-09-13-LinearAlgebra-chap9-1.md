---
layout: post
title: "9.1 확률분포의 추정"
date: 2021-09-13 15:35:28 -0400
categories: [데이터 사이언스 수학]
tags: [확률론]
comments: true
math: true
---

### 확률분포의 결정
- 확률분포 파악 과정 
    1. 확률변수가 어떤 확률분포를 따르는지 확인
        - 데이터가 0 또는 1 $$\rightarrow$$ 베르누이분포
        - 데이터가 카테고리 값 $$\rightarrow$$ 카테고라분포
        - 데이터가 0과 1 사이의 실수 $$\rightarrow$$ 배터분포
        - 데이터가 항상 0 이상 $$\rightarrow$$ 로그정규분포, 감마분포, F분포, 카이제곱분포, 지수분포, 하프코시분포 등
        - 데이터가 크기 제한이 없는 실수 $$\rightarrow$$ 정규분포, 스튜던트 t분포, 코시분포, 라플라스분포
        - (예외가 있을 수 있음)
    2. 데이터로부터 해당 확률분포의 모수의 값을 구함

### 모수 추정 방법론
- 모수 추정(parameter estimation): 모수값으로 가장 가능성이 높은 하나의 숫자를 찾는 것
- 종류
    - 모멘트 방법
    - 최대가능도 추정법
    - 베이즈 추정법

### 모멘트 방법
- 포본자료에 대한 표본모멘트가 확률분포의 이론적 모멘트와 같다고 가정
- $$\mu = E[ X ] \triangleq \bar x = {1 \over N} \sum^N_{i=1}x_i$$ ($$N$$: 데이터 갯수, $$x_i$$: 표본 데이터)
- $$\sigma^2 = E[ (X-\mu)^2 ] \triangleq \bar s^2 = {1 \over N-1} \sum^N_{i=1} (x_i - \bar x)^2$$ (분산 = 2차 모멘트)
- ex) 베르누이분포의 모수 추정
    - $$E[ X ] = \mu \triangleq \bar x = {1 \over N} \sum^N_{i=1} x_i = {N_1 \over N}$$ ($$N_1$$: 1의 갯수) 
- ex) 정규분포의 모수 추정
    - $$E[ X ] = \mu \triangleq \bar x = {1 \over N} \sum^N_{i=1} x_i$$
    - $$E[ (X-\mu)^2 ] = \sigma^2 \triangleq s^2 = {1 \over N-1} \sum^N_{i=1} (x_i - \bar x)^2$$
- ex) 베타 분포의 모수 추정
    - $$E[ X ] = {a \over a+b} \triangleq \bar x$$
    - $$E[ (X-\mu)^2 ] = {ab \over (a+b)^2(a+b+1)} \triangleq s^2$$
    - $$a = \bar x({\bar x(1- \bar x) \over s^2} - 1)$$
    - $$b = (1-\bar x)({\bar x(1- \bar x) \over s^2} - 1)$$

### 연습문제
- 9.1.1
    - ```python
      # CRIM: 
      # ZN: 
      # INDUS: </br>
      # CHAS: 베르누이분포 </br>
      # NOX: 베터분포 </br>
      # RM: </br>
      # AGE: </br>
      # DIS: </br>
      # RAD: </br>
      # TAX: </br>
      # PTRATIO: </br>
      # B: </br>
      # LSTAT: </br>
      # NEDV: </br>
      ```
- 9.1.2
    - ```python
      ```

<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요. 