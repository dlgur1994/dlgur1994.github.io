---
layout: post
title: "2.3 행렬의 성질"
date: 2021-07-30 16:50:28 -0400
categories: [선형대수학]
tags: [선형대수학]
comments: true
math: true
---

## 정부호와 준정부호
행렬 $$A$$가 영벡터가 아닌 모든 벡터 x에 대해,
양의 정부호: &nbsp;&nbsp;$$x^TAx > 0$$<br/>
양의 준정부호: &nbsp;&nbsp;$$x^TAx \geq 0$$<br/>
이는 대칭 행렬인 경우에만 주로 사용한다<br/>
<br/>
$$x^TAx = \begin{bmatrix}x_1 & x_2 & x_3\end{bmatrix} \begin{bmatrix}2 & -1 & 0 \\ -1 & 2 & -1 \\ 0 & -1 & 2\end{bmatrix} \begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix}$$
<br/>
$$= x_1^2 + (x_1 - x_2)^2 + (x_2 - x_3)^2 + x_3^2$$ 이므로<br/> 
$$x_1 = x_2 = x_3 = 0$$인 경우를 제외하고는 항상 $$0$$보다 크다<br/>

## 행렬 놈
요소별 행렬 놈(entrywise matrix norm)<br/>
: $$\|A\|_p = (\sum_i^N\sum_j^M|a_{ij}|^p)^{1/p}$$<br/>

프로베니우스 놈(Frobenius norm)<br/>
: p가 2인 놈<br/>
$$\|A\| = \|A\|_2 = \|A\|_F = \sqrt{\sum_i^N\sum_j^Ma_{ij}^2}$$<br/>
놈은 항상 0보다 같거나 크다<br/>
놈을 최소화하는 것은 벡터의 제곱합을 최소화하는 것과 같다<br/>
$$\|x\|^2 = \sum_{i=1}^Nx_i^2 = x^Tx$$<br/>

## 대각합
정방행렬에 대해서만 정의되며 대각원소의 합<br/>
$$tr(A) = a_{11} + a_{22} + \cdots + a_{NN} = \sum_{i=1}^Na_{ii}$$<br/>
음수가 될 수도 있음<br/>
성질 (c:스칼라, A,B,C: 행렬)
- $$tr(cA) = ctr(A)$$
- $$tr(A^T) = tr(A)$$
- $$tr(A+B) = tr(A) + tr(B)$$
- $$tr(AB) = tr(BA)$$
- $$tr(ABC) = tr(BCA) = tr(CAB)$$ &nbsp;&nbsp;-> trace trick

## 행렬식
: $$det(A), det A, |A|$$ &nbsp; (A: 정방행렬)<>
$$det([a]) = a$$<br/>
여인수 전개<br/>
: $$det(A) = \sum_{i=1}^N\{(-1)^{i+j_0}M_{ij_0\}a_{ij_0}}$$

## 연습문제
- 2.2.1
    ```python
    import numpy as np
    p = np.array([[100], [80], [50]])
    n = np.array([[3], [4], [5]])
    p.T @ n
    >>>
    [[870]]
    ```
- 2.2.2
    - ![2](/images/linearalgebra/2_2/2.png){: width="50%" height="50%"} 
- 2.2.3
- 2.2.4 
- 2.2.5
- 2.2.6
- 2.2.7


<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.