---
layout: post
title: "3.3 고유값 분해"
date: 2021-08-07 00:00:28 -0400
categories: [데이터 사이언스 스쿨 수학]
tags: [선형대수학]
comments: true
math: true
---

### 고유값과 고유벡터
- 정방 행렬 $$A$$에 대해 다음 식을 만족하는 영벡터가 아닌 벡터 $$v$$, 실수 $$\lambda$$ 를 찾을 수 있다고 가정하자. <br/>
$$Av = \lambda v$$ <br/>
$$\lambda$$: 고유값(eigenvalue)
$$v$$: 고유벡터(eigenvector)
고유값과 고유벡터를 찾는 작업: 고유분해(eigen-decomposition) or 고윳값 분해(eigenvalue decomposition)
- 행렬 $$A$$의 고유벡터는 행렬 $$A$$를 곱해서 변환을 해도 방향이 바뀌지 않는 벡터<br/>
고윳값은 변환된 고유벡터와 원래 고유벡터의 크기 비율 <br/>
$$Av- \lambda v = (A -\lambda I)v = 0$$
- 어떤 벡터 $$v$$가 고유벡터가 되면 이 벡터에 실수를 곱한 벡터 $$cv$$, 즉 $$v$$와 방향이 같은 벡터는 모두 고유벡터가 됨
    - $$A(cv) = cAv = c \lambda v = \lambda (cv)$$$
- 그래서 보통 고유벡터를 표시할 때는 길이가 1인 단위벡터가 되도록 졍규화를 함
    - $$v \over \| v \|$$ 
- 예시 <br/>
$$A = \begin{bmatrix} 1 & -2 \\ 2 & -3 \end{bmatrix}, \lambda = -1, v = \begin{bmatrix}1 \\ 1\end{bmatrix}$$ <br/>
$$Av = \begin{bmatrix} 1 & -2 \\ 2 & -3 \end{bmatrix} \begin{bmatrix}1 \\ 1\end{bmatrix} = \begin{bmatrix}-1 \\ -1\end{bmatrix} = (-1) \begin{bmatrix}1 \\ 1\end{bmatrix} = (-1) \begin{bmatrix} {\sqrt 2 \over 2} \\ {\sqrt 2 \over 2}\end{bmatrix} = \lambda v$$

### 특성방정식

### 고윳값의 개수
### 고윳값과 대각합/행렬식
### 고유벡터의 계산
### 넘파이를 사용한 고유분해
### 대각화
### 대각화가능
### 고윳값과 역행렬
### 대칭행렬의 고유분해
### 대칭행렬을 랭크-1 행렬의 합으로 분해
### 대칭행렬의 고윳값 부호
### 분산행렬
### 분산행렬의 역행렬
### 요약: 고유분해의 성질

### 연습문제
- 3.3.1
    - ![1](/images/linearalgebra/3_3/1.png){: width="50%" height="80%"} 

<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.