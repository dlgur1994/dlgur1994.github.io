---
layout: post
title: "6.3 확률의 성질"
date: 2021-08-10 22:38:28 -0400
categories: [데이터 사이언스 수학]
tags: [선형대수학]
comments: true
math: true
---

## 성질
1. 공집합의 확률
    - $$P(\emptyset) = 0$$
2. 여집합의 확률
    - $$P(A^C) = 1 - P(A)$$
3. 포함-배제 원리 (= 덧셈규칙)
    - $$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$ 
4. 전체 확률의 법칙
    - 조건
        - $$C_i \cap C_j = \emptyset (i \neq j)$$
        - $$C_1 \cup C_2 \cup \cdots = \Omega$$
    - $$P(A) = \sum_i P(A \cap C_i) = \sum_i P(A, C_i)$$

## 연습문제
- 6.3.1<br/>
    - $$A$$: 남자 집합
    - $$B$$: 머리카락이 긴 사람의 집합
    - $$C_i$$: 생일이 i월인 사람
- 6.3.2
    - 성질2: $$P(A^C) =$$ 여자 집합 $$= 1 -P(A)$$
    - 성질3: $$P(A \cup B) =$$ 남자 집합 + 머리카락이 긴 사람의 집합 - (둘다 포함되는 사람의 집합) $$= P(A) + P(B) - P(A \cap B)$$ 
    - 성질4: $$P(A) =$$ 생일이 1월인 남자 집합 + 생일이 2월인 남자 집합 + $$\cdots$$ + 12월이 생일인 남자 집합 $$= P(A \cap C_1) + P(A \cap C_2) + \cdots + P(A \cap C_12)$$


<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.