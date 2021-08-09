---
layout: post
title: "6.1 집합"
date: 2021-08-09 22:55:28 -0400
categories: [선형대수학]
tags: [선형대수학]
comments: true
math: true
---

## 집합과 원소
- 집합(set): 구별 가능한 객체의 모임 (보통 알파벳 대문자로 표기)
- 원소(element): 집합에 포함된 구별 가능한 객체 (보통 알파벳 소문자로 표기)
- 예시
    - $$x \in A$$
    - $$x \notin A$$
    - $$A = {1, 2, 3} \rightarrow 1 \in A, 4 \notin A$$ 

## 집합의 크기
- $$|A| = card(A)$$
- 실수 구간 집합은 무한개의 원소를 가진 집합이다.

## 합집합과 교집합
- 합집합(union): $$A \cup B$$
- 교집합(intersection): $$A \cap B$$

## 전체집합, 부분집합, 여집합
- 부분집합(subset): 어떤 집합의 원소 중 일부만을 포함하는 집합
- 전체집합: 원래의 집합
- $$A \subset \Omega$$
- $$A \subset A, for all A$$
- 진부분집합(proper subset): 원소의 크기가 더 작은 부분집합

## 차집합과 여집합
- 차집합(difference)
    - $$A - B$$
    - 집합 A에 속하면서 B에 속하지 않는 원소로 이루어진 부분집합
- 여집합(complement)
    - $$A^C$$
    - 집합 A에 속하지 않는 원소로만 이루어진 부분집합
    - $$A^C = U - A$$

## 공집합
- 공집합(null set): $$\emptyset$$
- $$\emptyset \subset A, for all A$$
- $$A \cap \emptyset = \emptyset$$
- $$A \cup \emptyset = A$$
- $$A \cap A^C = \emptyset$$

## 부분집합의 수
- $$2^N$$ (N: 원소의 갯수)

## 합집합과 교집합의 분배 법칙
- $$A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$$
- $$A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$$

## 연습문제
- 6.1.1<br/>
    1. $$2^4$$ = 16개
    2. 
    3. ```python
        A = frozenset(['HH', 'HT', 'TH', 'TT'])
        B = set([{}, 'HH', 'HT', 'TH', 'TT', ('HH', 'HT'), ('HH', 'TH'), ('HH', 'TT'), ('HT', 'TH'), ('HT', 'TT'), ('TH', 'TT'), ('HH', 'HT', 'TH'), ('HH', 'HT', 'TT'), ('HH', 'TH', 'TT'), ('HT', 'TH', 'TT'), ('HH', 'HT', 'TH', 'TT')])
        ```
- 6.1.2<br/>
    ```python
    A = {1, 3, 5}
    B = {1, 2, 3}
    C = {2, 4, 6}
    print(A | (B & C))
    print((A | B) & (A | C))
    print(A & (B | C))
    print((A & B) | (A & C))
    ```


<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.