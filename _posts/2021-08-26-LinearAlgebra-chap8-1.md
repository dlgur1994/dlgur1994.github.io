---
layout: post
title: "8.1 사이파이를 이용한 확률분포 분석"
date: 2021-08-26 00:00:28 -0400
categories: [데이터 사이언스 수학]
tags: [확률론]
comments: true
math: true
---

### 확률분포 클래스
- 이산
    - 베르누이분포
    - 이항분포
    - 다항분포
- 연속
    - 균일분포
    - 정규분포
    - 베타분포
    - 감마분포
    - 스튜던트 t분포
    - 카이 제곱분포
    - F분포
    - 디리클리분포
    - 다변수 정규분포

### 모수 지정
- 모수(parameter): 확률분포 객체를 생성할 때 분포의 형상을 구체적으로 지정 (기대값, 표준편차)

### 변환 확률변수의 시뮬레이션
- cf) 0과 1 사이의 균일분포를 가지는 확률변수에서 두 표본값을 생성하여 이 두 값을 합하면  균일분포가 아닌 1에서 최빈값을 가지는 삼각형 모양의 분포가 됨

### 연습문제
- 8.1.1
    1. ```python
        rv = sp.stats.norm(loc=0, scale=0.1)
        xx = np.linspace(-8, 8, 100)
        pdf = rv.pdf(xx)
        plt.plot(xx, pdf)
        plt.title("확률밀도함수 ")
        plt.xlabel("$x$")
        plt.ylabel("$p(x)$")
        plt.show()
       ```
    2. ```python
       max(pdf)
       
       # 2.8781544236067225
       ```
- 8.1.2
    - ```python
      rv = sp.stats.norm(loc=1, scale=2)
      print(sp.mean(rv.rvs(size=1000, random_state=17)))
      print(sp.var(rv.rvs(size=1000, random_state=17), ddof=0))
      
      # 1.0428874436834124
      # 4.148888780605581
      ```
- 8.1.3
    - ```python
      rv0 = sp.stats.uniform()
      rv1 = sp.stats.uniform()
      rv2 = sp.stats.uniform()
      rv3 = sp.stats.uniform()
      rv4 = sp.stats.uniform()
      rv5 = sp.stats.uniform()
      rv6 = sp.stats.uniform()
      rv7 = sp.stats.uniform()
      rv8 = sp.stats.uniform()
      rv9 = sp.stats.uniform()
      
      np.random.seed(17)
      N = 1000
      x_0 = rv0.rvs(N)
      x_1 = rv1.rvs(N)
      x_2 = rv2.rvs(N)
      x_3 = rv3.rvs(N)
      x_4 = rv4.rvs(N)
      x_5 = rv5.rvs(N)
      x_6 = rv6.rvs(N)
      x_7 = rv7.rvs(N)
      x_8 = rv8.rvs(N)
      x_9 = rv9.rvs(N)
      x_10 = x_0 + x_1 + x_2 + x_3 + x_4 + x_5 + x_6 + x_7 + x_8 + x_9
    
      plt.figure(figsize=(12, 5))
      sns.distplot(x_10, kde=False)
      plt.title("균일분포 표본의 합의 분포")
      plt.xlabel("표본값")
      plt.xlim(2, 8)
      plt.show()
      ```
    
<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.