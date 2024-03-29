---
layout: post
title: "7.1 확률적 데이터와 확률변수"
date: 2021-08-17 23:00:28 -0400
categories: [데이터 사이언스 수학]
tags: [확률론]
comments: true
math: true
---

### 확률적 데이터
- 결정론적 데이터(deterministic data): 항상 같은 값이 나오는 데이터
- 확률적 데이터(random data, probabilistic data, stochastic data): 예측할 수 없는 값이 나오는 데이터
    - 여러 조건이나 상황에 따라 데이터 값이 영향을 받는다
    - 측정 시에 오차가 발생한다

### 분포
- 확률적 데이터에서 어떠한 값이 자주 나오고 어떠한 값이 드물게 나오는가를 나타내는 정보
    - count plot: 범주형 데이터
    - histogram: 실수형 데이터

### 기술통계
- 여러가지 숫자를 계산하여 분포의 특징을 나태내는 방식
- 종류
    - 표본평균, 표본중앙값, 표본최빈값
    - 표본분산, 표본표준편차
    - 표본왜도, 표본첨도

### 표본평균
- 일반적으로 부르는 평균 ($$m \ or \ \bar x$$)
- $$m = \bar x = {1 \over N} \sum_{i=1}^N x_i$$

### 표본중앙값
- 전체 자료를 크기별로 정렬했을 때 가장 중앙에 위치하는 값
- N이 홀수: 중앙값 = $$(N+1)/2$$째 표본
- N이 짝수: 중앙값 = $$N/2$$째 표본과 $$N/2+1$$째 표본의 평균

### 표본최빈값
- 데이터 값 중 가장 빈번히 나오는 값(most frequent value, sample mode)
- 유한한 종류의 값이 존재하는 데이터에 적합
- 무한한 종류의 값이 존재하는 데이터의 경우, 구간을 나누어 최빈값을 사용한다. 기준에 따라 달라지기 때문에 신뢰도 떨어진다.

### 단봉분포와 다봉분포
- 단봉(uni-modal)분포: 분포의 모양에서 봉우리가 하나인 경우
- 다봉(multi-modal)분포: 분포의 모양에서 봉우리가 여럿인 경우

### 대칭분포
- 분포가 표본평군을 기준으로 대칭인 대칭분포
    - 표본중앙값 = 표본평균
- 분포가 대칭분포이면서 하나의 최고값만을 가지는 단봉분포
    - 표본최빈값 = 표본평균
- 대칭분포를 비대칭으로 만드는 데이터가 더해지면
    - 표본평균이 가장 크게 영향을 받음
    - 표본최빈값이 가장 적게 영향을 받음

### 분산과 표준편차
- 데이터가 얼마나 변동하고 있는지 나타내는 방법
    - 표본분산(sample variance)
    - 표본표준편차(sample standard deviatin)  
- $$standard \ deviation = \sqrt {variance}$$
- $$v_{biased} = s_{biased}^2 = {1 \over N} \sum_{i=1}^N (x_i - \bar x)^2$$
- $$v_{unbiased} = s_{unbiased}^2 = {1 \over N-1} \sum_{i=1}^N (x_i - \bar x)^2$$
    - 표본 분산이 모집단 분산에 맞춰서 동일하게 보정된 것  

### 표본비대칭도
- 표본비대칭도(sample skewness): 평균과의 거리의 세제곱을 이용하여 구한 특징값
- 표본비대칭도 = 0: 분포가 대칭
- 표본비대칭도 < 0: 표본평균값을 기준으로 왼쪽에 있는 값을 가진 표본이 나올 가능성이 크다
- $${ {1 \over N} \sum_{i=1}^N (x_i - \bar x)^3 \over {\sqrt{ {1 \over N-1} \sum_{i=1}^N (x_i - \bar x)^2}^3}}$$

### 표본첨도
- 표본첨도(sample kurtosis): 평균과의 거리의 네제곱을 이용하여 구한 특징값
- 데이터가 중앙에 몰려있는 정도를 정밀하게 비교하는데 쓰임
- 사람의 눈으로 첨도를 구별하는 것은 어려움
- 첨도 > 정규분포: 표본첨도 양수
- 첨도 < 정규분포: 표본첨도 음수
- $${ {1 \over N} \sum_{i=1}^N (x_i - \bar x)^4 \over ({1 \over N} \sum_{i=1}^N(x_i - \bar x)^2)^2} - 3$$

### 표본모멘트
- k차 표본모멘트(sample moment): k제곱을 이용하여 구한 모멘트
- $${1 \over N} \sum_{i=1}^N x_i^k$$
- 표본 중앙모멘트(sample centered moment): $${1 \over N} \sum_{i=1}^N (x_i - \bar x)^k$$ (2차 표본모멘트 이상)

### 확률변수
- 수학적으로 확률공간의 표본을 입력으로 받아서 실수인 숫자로 바꾸어 출력하는 함수
- $$\omega \in \Omega \rightarrow x \in R$$
- $$X(\omega) = x$$ ($$X$$: 확률변수)

### 이산확률변수
- 이산확률변수(discrete random variable): 확률변수값이 연속적이지 않고 떨어져 있도록 정의할 수 있는 경우 (e.g. $$X(a) = 1, X(b) = 2, X(c) = 3$$)
- 확률질량함수: 표본이 나올 가능성을 출력하는 함수 (e.g. $$p(a)= {1 \over 4}, p(b)= {2 \over 4}, p(c)= {1 \over 4}$$)
- 표본공간의 원소의 갯수가 무한대인 경우도 이산확률변수가 될 수 있음

### 연속확률변수
- 연속활률변수(continuous random variable): 연속적이고 무한대의 실수 표본값을 가지는 확률변수
- 모든 표본이 실수인 숫자로 변환되면 모든 사건은 구간사건의 조합으로 표시됨 (확률분포를 수학적인 확률밀도함수로 나타낼 수 있음)

### 확률변수와 실제 데이터
- 확률변수는 실수인 데이터를 생성하는 데이터생성기
    - 주사위에서 나오는 숫자는 1부터 6까지이고, 균일분포 확률분포함수를 가진 이산확률변수
    - 정상인의 최고혈압은 실수가 나오고, 120 mmHg 근처에서 기댓값을 가지는 단봉분포 모양의 확률분포함수를 가진 연속확률변수
- 표본화
    - 확률분포함수에 따라 표본공간의 표본이 현실 세계의 데이터로 선택되는 것 (= 실현, realization)
    - 데이터 집합에서 일부 데이터만 선택하는 과정
- 확률변수와 실제 데이터의 관계
    - 확률변수로부터 데이터를 여러 번 생성하는 경우 실제 데이터값은 매번 달라질 수 있지만 확률변수 자체는 변하지 않음
    - 확률변수의 확률분포함수는 직접 관찰할 수 없고, 확률변수에서 만들어지는 실제 데이터값을 이용하여 확률분포함수를 추정하는 것
    - 확률변수에서 만들어지는 실제 데이터값은 확률변수가 가진 특성을 반영하고 있음
    - 데이터 개수가 많을수록 확률분포함수를 정확하게 묘사할 수 있음

### 연습문제
- 7.1.1
    - 1 
        ```python
        df['petal length (cm)'].hist()
        plt.title("petal")
        plt.show()
        ```
        - 다봉분포
    - 2
        ```python
        df[df['species']=='setosa']['petal length (cm)'].hist()
        plt.title("petal")
        plt.show()
        ```
        - 단봉분포
- 7.1.2
    - 1
        ```python
        x = df[df['species']=='virginica']['petal length (cm)']
        bins = np.linspace(0, 10,  11)
        ns, _ = np.histogram(x, bins=bins)
        
        sample_mean = np.mean(x)
        sample_median = np.median(x)
        mode_index = np.argmax(ns)
        sample_mode = 0.5 * (bins[mode_index] + bins[mode_index + 1])
        
        print(sample_mean)
        print(sample_median)
        
        sns.displot(x, bins=bins)
        plt.axvline(sample_mean, c='k', ls=":", label="mean")
        plt.axvline(sample_median, c='k', ls="--", label="median")
        plt.axvline(sample_mode, c='k', ls="-", label="most frequent value")
        plt.title("mean, median, most frequent value")
        plt.xlabel("petal length")
        plt.legend()
        plt.show()
        ```
    - 2
        범위가 더 세분화되어 분포가 달라진다 <br/>
        ```python
        x = df[df['species']=='virginica']['petal length (cm)']
        bins = np.linspace(0, 10,  101)
        ns, _ = np.histogram(x, bins=bins)
        
        sample_mean = np.mean(x)
        sample_median = np.median(x)
        mode_index = np.argmax(ns)
        sample_mode = 0.5 * (bins[mode_index] + bins[mode_index + 1])
        
        print(sample_mean)
        print(sample_median)
        
        sns.displot(x, bins=bins)
        plt.axvline(sample_mean, c='k', ls=":", label="mean")
        plt.axvline(sample_median, c='k', ls="--", label="median")
        plt.axvline(sample_mode, c='k', ls="-", label="most frequent value")
        plt.title("mean, median, most frequent value")
        plt.xlabel("petal length")
        plt.legend()
        plt.show()
        ```
- 7.1.3
    - 1
        ```python
        np.mean(r), np.var(r), np.std(r)
        
        # (0.0004713634116751941, 0.0001517048092072256, 0.012316850620480286) 
        ```
    - 2
        ```python
        av = np.std(r) * 0.16
        av
        
        # 0.001970696099276846
        ```

<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.