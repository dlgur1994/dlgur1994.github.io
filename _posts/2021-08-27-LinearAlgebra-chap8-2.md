---
layout: post
title: "8.2 베르누이분포와 이항분포"
date: 2021-08-27 00:00:00 -0400
categories: [데이터 사이언스 수학]
tags: [확률론]
comments: true
math: true
---

### 베르누이 시행
- 베르누이 시행(Bernoulli trial)
    - 결과가 두 가지 중 하나로만 나오는 실험이나 시행
    - ex) 동전을 던져 앞면 또는 뒷면이 나오는 실험

### 베르누이 확률변수
- 베르누이 확률변수(Bernoulli random variable)
    - 베르누이 시행의 결과를 실수 0 또는 1로 바꾼 것
    - 두 값 중 하나만 가질 수 있으므로 이산확률변수임
    - 1과 -1로 표현하는 경우도 있음

### 베르누이 확률분포
- 베르누이 확률분포 (베르누이분포)
    - 베르누이 확률변수의 분포
    - $$X \sim Bern(x: \mu)$$
- 베르누이분포의 확률질량함수
    - $$Bern(x; \mu) = \mu \ \ (if \ x =1), 1-\mu \ \ (if \ x =0)$$
    - ($$\mu$$= 1이 나올 확률인 모수이므로) 
    - $$Bern(x;\mu) = \mu^x(1-\mu)^{(1-x)}$$
    - (베르누이 확률변수 표본값이 1과 -1이라면)
    - $$Bern(x;\mu) = \mu^{(1+x)/2}(1-\mu)^{(1-x)/2}$$
- cf) 시뮬레이션(simulation): 확률변수의 표본을 생성하는 작업

### 베르누이분포의 모멘트
- 기댓값: $$E[ X ] = \mu$$
- 분산: $$Var[ X ] = \mu (1 - \mu)$$

### 이항분포
- 이항분포(binomial distribution)
    -  성공확률이 $$\mu$$인 베르누이 시행을 N번 반복하는 경우
    -  $$X \sim Bin(x:N, \mu)$$
-  베르누이분포와 이항분포는 모두 베르누이 확률변수에서 나온 표본값
-  표본 데이터가 하나: 베르누이분포
-  표본 데이터가 여럿: 이항분포
- 확률질량함수: $$Bin(x;N,\mu) = \binom N x \; \mu^x(1-\mu)^{N-x}$$

### 이항분포의 모멘트
- 기댓값: $$E[ X ] = N\mu$$
- 분산: $$Var[ X ] = N\mu(1-\mu)$$

### 베르누이분포와 이항분포의 모수추정
- 모수추정(parameter estimation)
    - 데이터에서 모수의 값을 찾아내는 것
    - $$\hat \mu = {\sum^N_{i=1}x_i \over N} = {N_1 \over N}$$ ($$N$$: 전체 데이터 수, $$N_1$$: 1이 나온 횟수)

### 베르누이분포의 활용
- 활용
    - 베이지안 관점: 분류예측 문제의 출력 데이터가 두 값으로 구분되는 카테고리값인 경우에 분류 결과 즉, 두 값 중 어느 값이 가능성이 높은지를 표현
    - 빈도주의적 관점: 입력 데이터가 0 또는 1 혹은 참 또는 거짓, 두 개의 값으로 구분되는 카테고리값인 경우, 두 종류의 값이 나타나는 비율을 표현
    - 예) 스팸메일 구분 

### 연습문제
- 8.2.1
    - $$Bern(x;\mu) = \mu^x(1-\mu)^{(1-x)}$$
    - $$x=1, Bern(1;\mu) = \mu$$
    - $$x=0, Bern(0;\mu) = (1-\mu)$$
- 8.2.2
    ```python
    mu = 0.6 # 0.9
    rv = sp.stats.bernoulli(mu)
    xx = [0, 1]
    x = rv.rvs(10, random_state=17) # 1000
    y = np.bincount(x, minlength=2) / float(len(x))
    
    df = pd.DataFrame({"이론": rv.pmf(xx), "시뮬레이션": y})
    df.index = [0, 1]
    df2 = df.stack().reset_index()
    df2.columns = ["표본값", "유형", "비율"]
    
    sns.barplot(x="표본값", y="비율", hue="유형", data=df2)
    plt.title("베르누이분포의 이론적 분포와 시뮬레이션 분포")
    plt.show()
    ```
- 8.2.3
    ```python
    N = 5 # 20
    mu = 0.5 # 0.9
    rv = sp.stats.binom(N, mu)
    xx = np.arange(N + 1)
    
    np.random.seed(17)
    x = rv.rvs(10) # 1000
    
    y = np.bincount(x, minlength=N+1)/float(len(x))
    df = pd.DataFrame({"이론": rv.pmf(xx), "시뮬레이션": y}).stack()
    df = df.reset_index()
    df.columns = ["표본값", "유형", "비율"]
    df.pivot("표본값", "유형", "비율")
    
    sns.barplot(x="표본값", y="비율", hue="유형", data=df)
    plt.title("이항분포의 이론적 분포와 시뮬레이션 분포")
    plt.show()
    ```
- 8.2.4
    1. <0, 1/5, 3/5, 1>, 
    2. 
    
<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.