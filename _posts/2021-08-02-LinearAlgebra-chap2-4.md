---
layout: post
title: "2.4 선형 연립방정식과 역행렬"
date: 2021-08-02 17:43:28 -0400
categories: [선형대수학]
tags: [선형대수학]
comments: true
math: true
---

## 선형 연립방정식
- 복수의 미지수를 포함하는 복수의 선형 방정식 (= 연립일차방정식)
- $$a_{11}x_1 + a_{12}x_2 + \cdots + a_{1M}x_M = b_1$$<br/>
$$a_{21}x_1 + a_{22}x_2 + \cdots + a_{2M}x_M = b_2$$<br/>
&nbsp;&nbsp;&nbsp;&nbsp;$$\vdots$$ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $$\vdots$$ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $$\vdots$$ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $$\vdots$$<br/>
$$a_{N1}x_1 + a_{N2}x_2 + \cdots + a_{NM}x_M = b_N$$
- <div style="text-align: left"> $$\begin{bmatrix}a_{11} & a_{12} & \cdots & a_{1M} \\ a_{11} & a_{12} & \cdots & a_{1M} \\ \vdots & \vdots & \vdots & \vdots\\ a_{N1} & a_{N2} & \cdots & a_{NM}\end{bmatrix} \begin{bmatrix}x_1 \\ x_2 \\ \vdots \\ x_M\end{bmatrix} = \begin{bmatrix}b_1 \\ b_2 \\ \vdots \\ b_M\end{bmatrix}$$ </div>
- $$A = \begin{bmatrix}a_{11} & a_{12} & \cdots & a_{1M} \\ a_{11} & a_{12} & \cdots & a_{1M} \\ \vdots & \vdots & \vdots & \vdots\\ a_{N1} & a_{N2} & \cdots & a_{NM}\end{bmatrix}$$, $$x = \begin{bmatrix}x_1 \\ x_2 \\ \vdots \\ x_M\end{bmatrix}$$, $$b = \begin{bmatrix}b_1 \\ b_2 \\ \vdots \\ b_M\end{bmatrix}$$
- $$A$$: 계수행렬(coefficient matrix), $$x$$: 미지수벡터(unknown vector), $$b$$: 상수벡터(constant vector)
- $$Ax = b$$ ($$x \neq {b \over A}$$, 스칼라가 아니기 때문에 역행렬 이용해야 함)

## 역행렬
- $$A^{-1}$$
- $$A^{-1}A = AA^{-1} = I$$
- 행렬 A에 따라서 존재하지 않을 수도 있다.
- 가역행렬(invertible matrix): 역행렬이 존재하는 행렬
- 비가역행렬(non-invertible matrix): 역행렬이 존재하지 않는 행렬

## 역행렬의 성질
$$A^{-1}, B^{-1}, C^{-1}$$ 이 존재하면,
- $$(A^T)^{-1} = (A^{-1})^T$$
- $$(AB)^{-1} = B^{-1}A^{-1}$$
- $$(ABC)^{-1} = C^{-1}B^{-1}A^{-1}$$

## 역행렬의 계산
- $$A^{-1} = {1 \over {det(A)}}C^T = {1 \over {det(A)}}\begin{bmatrix}C_{1,1} & \cdots & C_{N,1} \\ \vdots & \vdots & \vdots \\ C_{1,N} & \cdots & C_{N,N}\end{bmatrix}$$
- $$C_{i,j}$$: A의 i, j번째 원소에 대해 정의한 cofactor
- $$C$$: 여인수행렬(matrix of cofactors)
- $$C^T$$: 수반행렬(adjoint matrix, adjugate matrix) (=$$adj(A)$$)
- $$det(A) = 0$$ 이면 역행렬이 존재하지 않는다

## 역행렬에 대한 정리
- Sherman-Morrison 공식
    - 정방행렬 $$A$$, 벡터 $$u, v$$에 대해<br/>
    $$(A + uv^T)^{-1} = A^{-1} - { {A^{-1}uv^TA^{-1}} \over {1 + v^TA^{-1}u} }$$
    
- Woodbury 공식
    - $$\begin{bmatrix}A_{11} & A_{12} \\ A_{21} & A_{22} \end{bmatrix}^{-1} = \begin{bmatrix}A_{11}^{-1}(I + A_{12}FA_{11}^{-1}) & -A_{11}^{-1}A_{12}F \\ -FA_{21}A_{11}^{-1} & F\end{bmatrix}$$
    - $$F = (A_{22} - A_{21}A_{11}^{-1}A_{12})^{-1}$$ or $$(A_{11} - A_{12}A_{22}^{-1}A_{21})^{-1}$$

## 역행렬과 선형 연립방정식의 해
- 행렬 A의 역행렬이 존재한다면,<br/>
$$Ax = b$$<br/>
$$A^{-1}Ax = A^{-1}b$$<br/>
$$Ix = A^{-1}b$$<br/>
$$x = A^{-1}b$$

## 선형 연립방정식과 선형 예측모형
- $$x_{11}w_1 + x_{12}w_2 + \cdots + x_{1N}w_N = y_1$$<br/>
$$x_{21}w_1 + x_{22}w_2 + \cdots + x_{2N}w_N = y_2$$<br/>
&nbsp;&nbsp;&nbsp;&nbsp;$$\vdots$$ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $$\vdots$$ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $$\vdots$$ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $$\vdots$$<br/>
$$x_{N1}w_1 + x_{N2}w_2 + \cdots + x_{NN}w_N = y_N$$
- $$Xw = y$$ ($$X$$: 계수행렬, $$w$$: 미지수벡터, $$y$$: 상수벡터)
- 역행렬이 있다면,<br/>
$$w = X^{-1}y$$

## 미지수의 수와 방정식의 수
1. 방정식의 수가 미지수의 수와 같다 (N = M)
    - 한 개의 해 존재 
2. 방정식의 수가 미지수의 수보다 적다 (N < M)
    - 무수히 많은 해가 존재
3. 방정식의 수가 미지수의 수보다 많다 (N > M)
    - 모든 조건을 만족하는 해가 하나도 존재할 수 없다 

## 최소자승문제
- 선형 연립방정식의 해가 존재하지 않을 때, 해가 정확하게 떨어지지 않아도 된다면<br/>
$$x_1 + x_2 = 2$$<br/>
$$x_2 + x_3 = 2$$<br/>
$$x_1 + x_2 + x_3 = 3$$<br/>
$$x_1 + x_2 + 2x_3 = 4 \approx 4.1$$<br/>
- $$e = Ax - b$$ ($$e$$: 잔차)<br/> 
$$e^Te = \|e\|^2 = (Ax - b)^T(Ax - b)$$ = 벡터 $$e$$의 놈을 최소화 하는 문제<br/>
$$x = argmin_x e^Te = arg min_x (Ax - b)^T(Ax - b)$$<br/> 
$$arg min_xf(x)$$: f(X)를 가장 작게 만드는 $$x$$<br/> 
=> **최소자승문제(least square problem)**
- $$Ax \approx b$$<br/>
두 벡터가 같다고 가정한다면,<br/>
$$A^TAx = A^Tb$$<br/>
$$(A^TA)^{-1}$$ 이 존재한다면,<br/>
$$(A^TA)^{-1}(A^TA)x = (A^TA)^{-1}A^Tb$$<br/>
$$x = ((A^TA)^{-1}A^T)b$$
- 행렬 A의 의사역행렬(pseudo inverse)<br/> 
$$A^+ = (A^TA)^{-1})A^T$$<br/>
$$x = A^+b$$

## 연습문제
- 2.4.1
    - ![1](/images/linearalgebra/2_4/1.png){: width="40%" height="40%"} 
- 2.4.2
    - ![2](/images/linearalgebra/2_4/2.png){: width="70%" height="60%"} 
- 2.4.3
    - ![3](/images/linearalgebra/2_4/3.png){: width="60%" height="100%"} 
- 2.4.4
    - ![4](/images/linearalgebra/2_4/4.png){: width="60%" height="60%"}
- 2.4.5
    ```python
    from sklearn.datasets import load_boston
    import numpy as np

    boston = load_boston()
    X = boston.data
    y = boston.target
    A = X[:4, [0, 4, 5, 6]]
    b = y[:4]

    np.linalg.inv(A) @ b
    >>>
    array([-3.12710043e+02, -1.15193942e+02,  1.44996465e+01, -1.13259317e-01])
    ```
- 2.4.6
    ```python
    from sklearn.datasets import load_boston
    import numpy as np

    boston = load_boston()
    X = boston.data
    y = boston.target

    (np.linalg.inv(X.T@X) @ X.T) @ y
    >>>
    array([-9.28965170e-02,  4.87149552e-02, -4.05997958e-03,  2.85399882e+00,
           -2.86843637e+00,  5.92814778e+00, -7.26933458e-03, -9.68514157e-01,
           1.71151128e-01, -9.39621540e-03, -3.92190926e-01,  1.49056102e-02,
           -4.16304471e-01])
    ```

<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.