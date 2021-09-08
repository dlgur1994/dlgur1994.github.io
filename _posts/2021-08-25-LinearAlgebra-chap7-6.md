---
layout: post
title: "7.6 조건부기댓값과 예측 문제"
date: 2021-08-23 23:22:28 -0400
categories: [데이터 사이언스 수학]
tags: [확률론]
comments: true
math: true
---

### 조건부 기댓값
- 조건부 기댓값(conditional expectation)
    - 확률변수 Y의 기댓값을 구할 때 주변 확률밀도함수 $$p_y(y)$$ 를 사용하여 가중치를 계산하지 않고 조건부 확률밀도함수 $$p_{y \vert x}(y \vert x)$$ 를 이용하여 가중치를 계산한 경우
    - = 조건부 평균(conditional mean)
    - $$E_y[Y \vert X] = \int_{y=- \infty}^{y=\infty} yp_{Y \vert X}(y \vert x)dy$$
    - $$E[Y \vert X] = \int yp(y \vert x)dy$$
    - 확률변수 X의 값 x는 사용자가 지정해야하는 독립변수이므로 조건부 기대값은 조건이 되는 확률 변수의 값에 따라서 값이 달라지는 확률변수
    - $$E[Y \vert X]$$ 는 조건이 되는 확률변수 X의 값 x를 입력으로 가지는 함수
        - $$E[Y \vert X = x] = f(x)$$
        - $$E[Y \vert x] = f(x)$$
        - $$f(x)$$: 확률변수 X의 값 x를 입력받아 확률변수 Y의 기대값을 출력하는 함수

### 예측 문제
- 예측 문제(prediction): 두 확률변수 X, Y에서 X의 값을 통해 Y의 값을 알아내는 것
- Y = 연속활률 $$\rightarrow$$ 회귀분석(regression analysis)
- Y = 이산확률변수 $$\rightarrow$$ 분류(classification)
- 예측 문제의 답($$\hat y$$): 조건부 기댓값, 중앙값, 최빈값 등
- $$x \rightarrow \hat y = E[y \vert x] = f(x)$$

### 조건부기댓값의 성질
- 조건부 기댓값 $$E[Y \vert X]$$ 가 $$X$$의 함수, 즉 변환이므로 조건부 기댓값도 확률변수다
- 만약 확률변수 $$Y$$가 확률변수 $$X$$의 값을 독립변수로 하는 결정론적 함수값이라면 <br/>
$$Y = g(X)$$ <br/>
$$X$$의 값을 어떤 값 $$x$$로 정하는 순간 $$Y$$의 값도 정해지기 때문에 $$Y = g(X)$$ 는 확률값이 아닌 상수가 된다 <br/>
$$E[Y \vert X] = E[g(x) \vert X] = g(X)$$ <br/>
같은 방식으로 확률변수 X와 Y가 결정론적 함수 관계가 아닐 때도 다음 등식이 성립 <br/>
$$E[g(X)Y \vert X] = g(X)E[Y \vert X]$$

### 전체 기댓값의 법칙
- 조건부 기댓값은 확률변수이므로 조건이 되는 확률변수에 대해 다시 기댓값을 구할 수 있고, 이를 반복하여 구한 조건부 기댓값의 기댓값은 원래 확률변수의 기대값과 같음
- $$E_X[E_Y[Y \vert X]] = E_Y[Y]$$
- $$E[E[Y \vert X]] = E[Y]$$

### 조건부분산
- $$x$$에 대한 조건부 확률분포 $$p(y \vert x)$$ 의 분산
- 예측문제의 관점에서 조건부 분산은 예측의 불확실성, 예측으로 맞출 수 없는 범위를 뜻함
- $$Var_y[Y \vert X] = E_Y[(Y-E_Y[Y \vert X])^2 \vert X] = \int (Y-E_Y[Y \vert X])^2 f_{Y \vert X} (y \vert x) dy$$

### 전체 분산의 법칙
- $$Var[Y] = E[Var[Y \vert X]] + Var[E[Y[X]]]$$
- $$E[Y \vert X] = \hat y \rightarrow Var[Y] = E[(\hat y -y)^2] + Var[\hat y]$$
- $$E[(\hat y - y)^2]$$: 예측 오차 즉, 편향의 평균적인 크기를 의미
- $$Var[\hat y]$$: 예측값의 변동 크기
- 예측값의 변동 크기가 증가하면 예측모형이 복잡하고 비선형적이며 주어진 데이터에 과최적화되기 쉽다는 것을 의미
- 따라서 전체 분산의 법칙은 예측 오차의 크기가 예측값의 변동의 합이 일정하므로 예측 오차를 줄미녀 모형이 복잡해지고 과최적화가 되며 반대로 모형을 과최적화를 막기 위해 단순하게 하면 예측 오차가 증가한다 (=편향-분산 상충(Bias-variance Tradeoff))

### 연습문제
- 7.6.1
    - ![1](/images/linearalgebra/7_6/1.png){: width="100%" height="100%"}

<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.