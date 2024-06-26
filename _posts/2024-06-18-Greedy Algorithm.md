---
layout: single
title: "[Algorithm] 그리디 알고리즘 (탐욕법)"
excerpt_separator: <!--break-->
categories:
  - "Algorithm"
date: 2024-06-18
toc: true
toc_sticky: true
sidebar:
  nav: "docs"
---

그리디 알고리즘(탐욕법)에 대해 알아보겠습니다.

<!--break-->

<br>

## 그리디 알고리즘

- 단순하지만 강력한 문제 해결 방법
- 현재 가장 좋은 것만 선택하는 방법
- 선택이 나중에 미칠 영향을 고려하지 않음

<br>

## 그리디 알고리즘 해결 방법

- 문제 풀이를 위한 최소한의 아이디어 구상하기
- 문제의 해가 정당한지 검토하기

<br>

## 그리디 알고리즘 예제

그리디 알고리즘의 대표적인 문제인 거스름돈 문제

> 500원, 100원, 50원, 10원 동전이 무한히 있다.
> 거슬러 줘야 할 돈이 1,260원일 때 거슬러 줘야 할 동전의 최소 개수는 몇 개인가?

### 코드

```python
N = 1260
count = 0

coin_types = [500, 100, 50, 10]

for coin in coin_types:
  count += N // coin
  N %= coin

결과값
6
```

### 설명

- 변수

  - N: 거스름돈
  - count: 거슬러줄 동전의 갯수
  - coin_types: 동전의 종류

- 과정

  ```python
  for coin in coin_types:   // 동전의 종류에 대해 반복
  count += N // coin        //  거스름돈을 현재 동전으로 나눈 몫을 count에 더함
  N %= coin                 //  거스름돈을 현재 동전으로 나눈 나머지를 거스름돈으로 저장
  ```
