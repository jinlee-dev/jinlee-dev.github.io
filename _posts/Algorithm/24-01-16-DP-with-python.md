---
layout: single
title:  "Python으로 구현하는 DP"
category: Algorithm
tags: [Algorithm, Python, DP]
date: 2024-01-16
comments : true
---

## DP란?
주어진 문제를 여러 개의 부분 문제들로 나누어 푼 다음, 그 결과들로 주어진 문제를 푸는 알고리즘.
아주아주 빈도가 높기 때문에 꼭 알아둬야 하고, 난이도가 천차만별인 문제이기도 함.
점화식만 파악하면 쉬운데...

## 분할 정복과의 차이점
분할 정복의 경우, 문제를 분할 했을 때 중복 Case가 없지만, DP는 중복 케이스가 있어 메모이제이션을 해야 한다.

## 그리디 알고리즘과의 차이점
그리디 알고리즘보다 DP가 느리지만, 정확한 값을 얻을 수 있다.

## 메모이제이션
컴퓨터 프로그램이 동일한 계산을 반복해야 할 때, 이전에 계산한 값을 메모리에 저장함으로써 동일한 계산의 반복 수행을 제거하여 프로그램 실행 속도를 빠르게 하는 기술
```
for i in range(2, x + 1):
    if i % 3 == 0:
        dp[i] = min(dp[i] , dp[int(i / 3)] + 1)
    if i % 2 == 0:
        dp[i] = min(dp[i] ,dp[int(i / 2)] + 1)
    dp[i] = min(dp[i] ,dp[i - 1] + 1)
```
위 코드에서 이전에 계산해 뒀던 `dp[i - 1]` `dp[int(i / 3)]` `dp[int(i / 2)]` 를 사용하여 연산량을 줄이는 것을 메모이제이션이라고 함

## 탑다운 방식과 바텀업 방식
### 탑다운 방식
재귀 호출을 사용하여 푸는 방식
가독성이 좋고, 점화식을 이해하기 쉽다.
### 바텀업 방식
반복문을 사용하는 방식
가독성이 좀 떨어지긴 하지만, 시간과 메모리를 절약할 수 있다.