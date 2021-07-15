---
layout: post
title: "2.1 데이터와 행렬"
date: 2021-07-15 15:56:28 -0400
categories: [선형대수학]
tags: [선형대수학]
comments: true
math: true
---

### 선형대수
선형대수를 통해 많은 양의 데이터가 있는 경우에도 간단한 계산식으로 표현 할 수 있다.
```python
# 파이썬으로 선형대수를 사용하기 위한 기본 패키지
import numpy as np 
import matplotlib.pylab as plt
```

### 데이터의 유형
스칼라(scalar)
- 숫자 하나로 이루어진 데이터
- $$x \in R$$ (R: 실수)

벡터(vector)
- 여러 숫자로 이루어진 데이터 (= data record)
- 복수의 행과 하나의 열
- 벡터의 차원: 데이터 갯수
- $$x = \overrightarrow{x} = \begin{bmatrix}x_1\\x_2\\\vdots\\x_N\end{bmatrix}= x \in R^N : n$$ 차원 벡터
- $$x_i$$ 는 항상 스칼라가 아니고 벡터일 수도 있다.
- 특징 벡터: 벡터 데이터가 입력 데이터로 사용되는 경우
- 넘파이를 사용한 벡터 표현
    ```python
    # numpy의 array 사용 (벡터의 차원 $$\neq$$ 배열의 차원)
    # 벡터 x를 2차원 배열로 표기
    # numpy는 1차원 배열 객체도 벡터로 인정 (박터가 하나의 행으로 되어도 실제로는 열이다)
    x = np.array([[5.1], [3.5], [1.4], [0.2]])
    x
    >>>
    array([[5.1],
           [3.5],
           [1.4],
           [0.2]])
    ```

행렬(matrix)
- 여러개의 벡터로 이루어진 데이터
- $$X = \begin{bmatrix}x_{1,1} && x_{1,2} && \cdots && x_{1,N}\\x_{2,1} && x_{2,2} && \cdots && x_{2,N}\\\vdots && \vdots && \cdots && \vdots\\x_{N,1} && x_{N,2} && \cdots && x_{N,N}\end{bmatrix}$$
- 원소: $$x_{i,j}$$ or $$x_{ij}$$
- 여러 개의 데이터 레코드를 행렬로 나타날 때는 하나의 데이터 레코드가 하나의 행
- $$X \in R^{row \times col}$$
- 하나의 벡터는 열의 갯수가 1인 행렬이기도 하므로 열벡터라고도 부른다. (스칼라와 벡터 모두 행렬에 속한다)
    - 스칼라: $$a \in R^{1 \times 1}$$
    - 벡터: $$x \in R^{4 \times 1}$$
    ```python
    # ndarray 객체 사용
    A = np.array([[11,12,13], [21,22,23]])
    A
    >>>
    array([[11, 12, 13],
           [21, 22,23]])
    ```

### 텐서
같은 크기의 행렬 여러 개로 이루어진 데이터 (엄격한 수학적 정의로는 다르다)
컬러 이미지인 경우 빨강, 초록, 파랑을 표현하는 3개의 채널이 있다. (= 3차원 텐서)

### 전치 연산
행렬의 행과 열을 바꾸는 연산<br/>
$$x \rightarrow x^T$$ 또는 $$x \rightarrow x^\prime$$<br/>
$$x = \begin{bmatrix}x_1\\x_2\\\vdots\\x_N\end{bmatrix} \rightarrow x^T = \begin{bmatrix}x_1 x_2 \cdots x_N\end{bmatrix}$$
```python
# 1차원 ndarray는 전치 연산이 정의되지 않는다
A = np.array([[11,12,13], [21,22,23]])
A.T
>>>
array([[11, 21],
       [12, 22],
       [13, 23]])
```

### 행렬의 행 표기법과 열 표기법
행렬은 행 벡터 또는 열 벡터를 합친 형태로 표기할 수도 있다.

### 특수한 벡터와 행렬
#### 영벡터
: 모든 원소가 0인 N차원 벡터
$$0_N = 0 = \begin{bmatrix}0\\0\\\vdots\\0\end{bmatrix}$$
$$0 \in R^{N \times 1}$$ (N이 파악가능하면 생략 가능)
    ```python
    np.zeros((3, 1))
    >>>
    array([[0.],
           [0.],
           [0.]])
    ```

##### 일벡터
: 모든 원소가 1인 N차원 벡터
$$1_N = 1 = \begin{bmatrix}1\\1\\\vdots\\1\end{bmatrix}$$
$$1 \in R^{N \times 1}$$ (N이 파악가능하면 생략 가능)
    ```python
    np.ones((3, 1))
    >>>
    array([[1.],
           [1.],
           [1.]])
    ```

정방행렬
: 행의 갯수와 열의 갯수가 같은 행렬

대각행렬
: 모든 비대각 요소가 0인 행렬 (정방행렬이 아니여도 됨)
(주)대각: 행과 열이 같은 위치
비대각: 나머지
$$D = \begin{bmatrix}d_1 && 0 && \cdots && 0\\0 && d_2 && \cdots && 0\\\vdots && \vdots && \dots && \vdots\\0 && 0 && \cdots && d_N\end{bmatrix}$$

항등행렬
: 대각 행렬 중에서 모든 대각성분이 1인 대각행렬
$$I = \begin{bmatrix}1 && 0 && \cdots && 0\\0 && 1 && \cdots && 0\\\vdots && \vdots && \dots && \vdots\\0 && 0 && \cdots && 1\end{bmatrix}$$
    ```python
    np.identity(3)
    >>>
    array([[1., 0., 0.],
           [0., 1., 0.],
           [0., 0., 1.]])
    
    np.eye(3)
    >>>
    array([[1., 0., 0.],
           [0., 1., 0.],
           [0., 0., 1.]])
    ```

대칭행렬
: 행렬의 전치연산 후에도 원래 행렬과 같은 행렬 (정방행렬만 대칭행렬이 될 수 있음)
$$S^T = S$$
$$S \in R^{N \times N}$$

<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)의 수학편을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.