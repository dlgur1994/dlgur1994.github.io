---
layout: post
title: "1.2 수열과 집합의 합과 곱"
date: 2021-07-13 21:19:28 -0400
categories: [선형대수학]
tags: [선형대수학]
comments: true
use_math: true
---

### 수열
수열: 문자, 숫자, 변수등이 나열된 것으로 순서에 영향이 있다.<br/>
$${x_1}, {x_2}, {x_3}, \dots, {x_n}$$ (아래첨자: 인덱스)<br/>

### 집합
집합: 문자, 숫자, 변수등이 나열된 것으로 순서가 중요하지 않다.<br/>
{$${x_1}, {x_2}, {x_3}, \dots, {x_n}$$} &nbsp;  또는 &nbsp;  $${x_{1:N}}$$ &nbsp;  또는 &nbsp;  {$${x_i}$$}$${_N}$$<br/>
원소 x가 실수일 때: $$x \in R$$<br/>
두 개의 실수일 때: $$(x_1,x_2) \in R \times R$$ &nbsp;  또는 &nbsp;  $$(x_1,x_2) \in R^2$$<br/>

### 수열의 합과 곱
수열의 합: $${x_1} + {x_2} + \dots + {x_N} = \sum_{i=1}^N x_i$$<br/>
수열의 곱: $$x_1 \cdot x_2 \cdot \dots \cdot x_N = \prod_{i=1}^N x_i$$<br/>
성질<br/>
(1) $$\sum_{i=1}^N x_i = \sum_{j=1}^N x_j$$<br/>
(2) $$\sum_{i=1}^N cx_i = c\sum_{i=1}^N x_i$$<br/>
(3) $$\sum_{i=1}^N (x_i + y_i) = \sum_{i=1}^N x_i + \sum_{i=1}^N y_i$$<br/>
(4) $$\sum_{i=1}^N \sum_{j=1}^M = \sum_{j=1}^M \sum_{i=1}^N$$<br/>
(5) $$\prod_{i=1}^N \prod_{j=1}^M = \prod_{j=1}^M \prod_{i=1}^N$$<br/>

### 집합의 합과 곱
집합 $$X = \{x_1, x_2, x_3\}$$ 이라면<br/>
$$\sum_{X} x = x_1 + x_2 + x_3$$<br/>
$$\prod_X x = x_1 \cdot x_2 \cdot x_3$$<br/>
집합 내의 연산 중 특정한 조건이 있는 경우 다음과 같이 사용하면 된다.<br/>
ex) $$\prod_{x \in X, x \neq 0} x$$<br/>

### 연습문제
- 1.2.1
    - (1) 
        - ![1](/images/linearalgebra/1_2/1.png){: width="100%" height="100%"}
    - (2)
        - ![2](/images/linearalgebra/1_2/2.png){: width="50%" height="50%"}
    - (3)
        - ![3](/images/linearalgebra/1_2/3.png){: width="50%" height="50%"}
    - (4)
        - ![4](/images/linearalgebra/1_2/4.png){: width="50%" height="50%"}
- 1.2.2
    - (1)
        - ![5](/images/linearalgebra/1_2/5.png){: width="50%" height="50%"}
    - (2)
        - ![6](/images/linearalgebra/1_2/6.png){: width="50%" height="50%"}
- 1.2.3
    - (1)
        - ![7](/images/linearalgebra/1_2/7.png){: width="50%" height="50%"}
    - (2)
        - ![8](/images/linearalgebra/1_2/8.png){: width="50%" height="50%"}
- 1.2.4 
    - ![9](/images/linearalgebra/1_2/9.png){: width="50%" height="50%"}

<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)의 수학편을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.