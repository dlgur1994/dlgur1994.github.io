---
layout: post
title: "6.5 결합확률과 조건부확률"
date: 2021-08-13 11:14:28 -0400
categories: [선형대수학]
tags: [선형대수학]
comments: true
math: true
---

## 결합확률과 조건부확률
- 결합확률(joint probability)
    - 사건 A와 B가 동시에 발생할 확률
    - $$P(A \cap B) \ or \ P(A, B)$$
- 주변확률(marginal probability)
    - 결합되지 않는 개별의 사건 확률
    - $$P(A) \ or \ P(B)$$
- 조건부확률(conditional probability)
    - B가 사실일 경우의 사건 A에 대한 확률
    - $$P(A|B)$$
    - $$P(A|B) = {P(A, B) \over P(B)}$$
        - 사건 B가 사실이므로 모든 가능한 표본은 사건 B에 포함되어야 한다. 즉, 새로운 실질적 표본공간은 $$\Omega_{new} \rightarrow B$$
        - 사건 A의 원소는 모두 사건 B의 원소도 되므로 사실상 사건 $$A \cap B$$의 원소가 된다. 즉, 새로운 실질적 $$A_{new} \rightarrow A \cap B$$가 된다.
        - 따라서 사건 A의 확률 즉, 신뢰도는 원래의 신뢰도(결합확률)를 새로운 표본공간의 신뢰도(확률)로 정규화한 값이라고 할 수 있다.

## 독립
- $$P(A, B) = P(A)P(B)$$ 가 성립하면 두 사건 A와 B는 서로 독립
- A와 B가 독립이라면 $$P(A \vert B) = {P(A,B) \over P(B)} = {P(A)P(B) \over P(B)} = P(A)$$

## 원인과 결과, 근거와 추론, 가정과 조건부 결론
- $$P(A, B) = P(A\|B)P(B)$$ (결합확률의 정의 이용)
- = A, B가 모두 발생할 확률은 B가 발생할 확률과 그 사건이 발생한 경우 다시 A가 발생할 경우의 곱
- 예제 
$$P(A, B, C) = P(A \cap B \cap C)$$
$$= P(A \cap (B \cap C))$$
$$= P(A|B \cap C) P(B \cap C)$$
$$= P(A|B, C)P(B,C)$$

## 사슬 법칙
- $$P(X_1, X_2) = P(X_1)P(X_2|X_1)$$
- $$P(X_1, X_2, X_3) = P(X_3|X_1, X_2)P(X_1, X_2) = P(X_1)P(X_2|X_1)P(X_3|X_1, X_2)$$
- $$\vdots$$
- $$P(X_1, \cdots, X_N) = P(X_1) \prod_{i=2}^N P(X_i|X_1, \cdots, X_{i-1})$$

## 확률변수
- 확률변수: 확률적인 숫자 값을 출력하는 변수 (알파벳 대문자로 표기)
- 예제
    - $$X$$: 성별, $$Y$$: 머리카락 긴지 짧은지
    - $$X = 0$$: 남자인 사건 ($$A$$)
    - $$X = 1$$: 여자인 사건 ($$A^C$$)
    - $$Y = 0$$: 머리카락이 긴 사건 ($$B$$)
    - $$Y = 1$$: 머리카락이 짧은 사건 ($$B^C$$)
    - $$P(X=0) = P(A)$$
    - $$P(X=0, Y=0) = P(A,B)$$
    - $$X, Y$$ 가 가질 수 있는 모든 사건의 조합에 대해 독립이 성립하면 $$X, Y$$는 독립
        - 주변확률의 곱과 결합확률을 비교 

## 피지엠파이 패키지
- 위 패키지를 통해 이산확률묘형을 구현할 수 있음
- ```python
    from pgmpy.factors.discrete import JointProbabilityDistribution as JPD
    # JPD(확률변수의 이름 리스트, 사건 수 리스트, 확률값 리스트)
    px = JPD(['X'], [2], np.array([12, 8]) / 20)
    print(px)
    
    >>>
    +------+--------+
    | X    |   P(X) |
    +======+========+
    | X(0) | 0.6000 |
    +------+--------+
    | X(1) | 0.4000 |
    +------+--------+
  ```

## 연습문제
- 6.5.1
    1. $$P(A|B^C) = {9 \over 20} \div {10 \over 20} = {9 \over 10}$$
    2. $$P(A^C|B) = {7 \over 20} \div {10 \over 20} = {7 \over 10}$$
    3. $$P(A^C|B^C) = {1 \over 20} \div {10 \over 20} = {1 \over 10}$$
    4. $$P(B|A) = {3 \over 20} \div {12 \over 20} = {1 \over 4}$$
    5. $$P(B|A^C) = {7 \over 20} \div {8 \over 20} = {7 \over 8}$$
    6. $$P(B^C|A) = {9 \over 20} \div {12 \over 20} = {3 \over 4}$$
    7. $$P(B^C|A^C) = {1 \over 20} \div {8 \over 20} = {1 \over 10}$$
- 6.5.2
    1. $$P(A|B^C) = {6 \over 20} \div {10 \over 20} = {3 \over 5}$$
    2. $$P(A^C|B) = {4 \over 20} \div {10 \over 20} = {2 \over 5}$$
    3. $$P(A^C|B^C) = {4 \over 20} \div {10 \over 20} = {2 \over 5}$$
    4. $$P(B|A) = {6 \over 20} \div {12 \over 20} = {1 \over 2}$$
    5. $$P(B|A^C) = {4 \over 20} \div {8 \over 20} = {1 \over 2}$$
    6. $$P(B^C|A) = {6 \over 20} \div {12 \over 20} = {1 \over 2}$$
    7. $$P(B^C|A^C) = {4 \over 20} \div {8 \over 20} = {1 \over 2}$$
- 6.5.3
    1. $$P(A, B, C, D)$$<br/>
    $$= P((A,B), (C,D))$$<br/>
    $$= P(A,B | C,D)P(C,D)$$
    2. $$P(A,B|C)P(C)$$<br/>
    $$= {P(A \cap B \cap C) \over P(C)} P(C)$$<br/>
    $$= P(A,B,C) = P(A, (B,C))$$<br/>
    $$= P(A|B,C)P(B,C)$$
    3. $$P(A,B,C|D,E)$$<br/>
    $$= P(A,B,C,D,E) \over P(D,E)$$<br/>
    $$= P(A,B|C,D,E)P(C,D,E) \over P(D,E)$$<br/>
    $$= P(A,B|C,D,E)P(C,D|E)P(E) \over P(D,E)$$
- 6.5.4
    - $$P(A,B|C) = {P(A \cap B \cap C) \over P(C)}$$<br/>
    $$= {P(A|B,C)P(B,C) \over P(C)}$$<br/>
    B와 C는 독립이므로<br/>
    $$= {P(A|B,C)P(B)P(C) \over P(C)}$$<br/>
    $$= P(A|B,C)P(B)$$<br/>
- 6.5.5
    - ![1](/images/linearalgebra/6_5/1.png){: width="100%" height="100%"}
- 6.5.6
    - ```python
        from pgmpy.factors.discrete import JointProbabilityDistribution as JPD
        pxy = JPD(['X', 'Y'], [2, 2], np.array([3, 9, 7, 1]) / 20)
        print(pxy)
    
        >>>
        +------+------+----------+
        | X    | Y    |   P(X,Y) |
        +======+======+==========+
        | X(0) | Y(0) |   0.1500 |
        +------+------+----------+
        | X(0) | Y(1) |   0.4500 |
        +------+------+----------+
        | X(1) | Y(0) |   0.3500 |
        +------+------+----------+
        | X(1) | Y(1) |   0.0500 |
        +------+------+----------+
      ```


<br/>
<br/>
이 글은 ['데이터 사이언스 스쿨 수학편'](https://datascienceschool.net/02%20mathematics/00.00%20소개의%20글.html)을 정리한 것입니다.
질문이나 오류가 있다면 댓글 남겨주세요.