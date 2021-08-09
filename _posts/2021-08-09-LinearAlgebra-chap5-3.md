---
layout: post
title: "5.3 선형계획법 문제와 이차계획법 문제"
date: 2021-08-09 13:50:28 -0400
categories: [선형대수학]
tags: [선형대수학]
comments: true
math: true
---

## 선형계획법 문제
- 선형계획법 문제: 방정식이나 부등식 제한 조건을 가지는 선형 모형의 값을 최소화하는 문제 (= LP 문제)
- 기본형
    - 목적함수: $$\arg \min_x c^Tx$$
    - 제한조건
        - $$Ax = b$$ (선형 연립방정식으로 된 등식 제한조건)
        - $$x \geq 0$$ (변수값이 모두 음수가 아니어야하는 부등식 제한조건)
- 정규형 (기본형 확장)
    - 목적함수: $$arg min_x c^Tx$$
    - 제한조건
        - $$Ax \leq b$$
        - $$x \geq 0$$
- 예제
    - 문제 
        - 제품 A와 제품 B 각각 100개 이상 생산해야 한다.
        - 시간은 500시간 밖에 없다.
        - 제품 A는 생산하는데 1시간이 걸리고 제품 B는 2시간이 걸린다.
        - 특정 부품이 9800개밖에 없다.
        - 제품 A는 생산하는데 특정 부품을 4개 필요로 하고 제품 B는 생산하는데 특정 부품을 5개 필요로 한다.
        - 제품 A의 이익은 하나당 3만원이고 제품 B의 이익은 하나당 5만원이다.
    - 목적함수
        - $$-3x_1 -5x_2$$ 
    - 제한조건
        - $$x_1 \geq 0, x_2 \geq 0$$
        - $$x_1 \geq 100$$
        - $$x_2 \geq 100$$
        - $$x_1 + 2x_2 \leq 500$$
        - $$4x_1 + 5x_2 \leq 9800$$
    - 정규형 선형계획법
        - $$\min_x \begin{bmatrix} -3 & -5 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}$$
        - $$\begin{bmatrix} -1  & 0 \\ 0 & -1 \\ 1 & 2 \\ 4 & 5 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} \leq \begin{bmatrix} -100 \\ -100 \\ 500 \\ 9800 \end{bmatrix}$$
        - $$\begin{bmatrix} x_1 \\ x_2 \end{bmatrix} \geq \begin{bmatrix} 0 \\ 0 \end{bmatrix}$$

## 사이파이를 이용한 선형계획법 문제 계산
- ```python
    linprog(c, A, b)
    # c: 목적함수의 계수 벡터
    # A: 등식 제한조건의 계수 행렬
    # b: 등식 제한조건의 상수 벡터
    ```

- ```python
    import scipy.optimize

    A = np.array([[-1, 0], [0, -1], [1, 2], [4, 5]])
    b = np.array([-100, -100, 500, 9800])
    c = np.array([-3, -5])
    
    result = sp.optimize.linprog(c, A, b)
    result
    >>>
    con: array([], dtype=float64)
    fun: -1400.0
    message: 'Optimization terminated successfully.'
    nit: 3
    slack: array([ 200.,    0.,    0., 8100.])
    status: 0
    success: True
    x: array([300., 100.])
    ```

## CVXPY를 이용한 선형계획법 문제 계산
- ```python
    import cvxpy as cp

    # 변수의 정의
    a = cp.Variable()  # A의 생산량
    b = cp.Variable()  # B의 생산량

    # 조건의 정의
    constraints = [
        a >= 100,  # A를 100개 이상 생산해야 한다.
        b >= 100,  # B를 100개 이상 생산해야 한다. 
        a + 2 * b <= 500, # 500시간 내에 생산해야 한다.
        4 * a + 5 * b <= 9800,  # 부품이 9800개 밖에 없다.
    ]
    
    # 문제의 정의
    obj = cp.Maximize(3 * a + 5 * b)
    prob = cp.Problem(obj, constraints)
    
    # 계산
    prob.solve() 
    
    # 결과
    print("상태:", prob.status)
    print("최적값:", a.value, b.value)
    
    >>>
    상태: optimal
    최적값: 299.99999999999983 100.00000000000001
    ```

### 이차계획법 문제
- 이차계획법 문제: 방정식이나 부등식 제한 조건을 가지는 일반화된 이차형식의 값을 최소화하는 문제 (잔차 제곱합을 최소화하는 예측 모형에 추가적인 제한조건이 있는 경우)
- 목적함수
    - $${1 \over 2} x^T Qx + c^T x$$
- 제한조건
    - $$Ax = b$$ (등식 제한조건)
    - $$x \geq 0$$ (부호 제한조건)
- 예제
    - 목적함수
        - $$\arg \min_x x_1^2$$
    - 제한조건
        - $$x_1 + x_2 = 1$$
    - 이차형식으로 변환
        - $$\arg \min_x {1 \over 2} \begin{bmatrix} x_1 & x_2 \end{bmatrix} \begin{bmatrix} 2 & 0 \\ 0 & 2 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} + \begin{bmatrix} 0 & 0 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}$$
        - $$\begin{bmatrix} 1 & 1 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} = 1$$

### CvxOpt를 이용한 이차계획법 문제 계산
- ndarray 배열을 CvxOpt의 matrix형으로 바꿔야 한다
- 정수형을 사용하지 못하므로 항상 부동소수점 실수가 되도록 명시해야 한다
- ```python
    from cvxopt import matrix, solvers
    
    Q = matrix(np.diag([2.0, 2.0]))
    c = matrix(np.array([0.0, 0.0]))
    A = matrix(np.array([[1.0, 1.0]]))
    b = matrix(np.array([[1.0]]))
    
    sol = solvers.qp(Q, c, A=A, b=b)
    np.array(sol['x'])
    
    >>>
    array([[0.5],
           [0.5]])
    ```

## 연습문제
- 5.3.1
    - ![1](/images/linearalgebra/5_3/1.png){: width="40%" height="40%"} 


<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.