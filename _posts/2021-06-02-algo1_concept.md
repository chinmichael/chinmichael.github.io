---
title: "[알고리즘 기초] 알고리즘이란?"
excerpt: ""

categories: 
    - Algorithm Basic
tags:
    - [Algorithm, Big O]

toc: true
toc_label: "목차"
toc_icon: "indent"
toc_sticky: true

date: 2021-06-02
last_modified_at: 2021-06-02
---
## 1. 알고리즘이란?
제가 참고한 책에서는 문제를 해결하기 위한 계산이나 작업의 순서라고 표현하고 있습니다.   
좀 더 쉽게(?) 표현하면 일정한 결과나 목적을 달성하기 위한 일련의 행위들 혹은 이를 정리한 것입니다.   

대표적인 예로 특정 값을 찾거나(탐색) 난잡한 배열을 정리하기(정렬) 등도 알고리즘에 속합니다.   

좋은 알고리즘은 재사용성도 높고 적절히 잘 선택해 사용하면 작업속도를 비약적으로 상승시켜줍니다.   
알고리즘은 컴퓨터 프로그램 前단계의 영역이지만 작업의 효율성을 높여주기 위해 필요한 알고리즘을     
컴퓨터가 실행할 수 있도록(기본명령의 조합으로) 알고리즘을 설계 및 구현해야 합니다.   

결국 저희가 할 일을 요약하면, 여느 때와 마찬가지로   
특정 작업을 위한 재사용성과 효율성이 높은 방식을 찾거나 설계해 코드로 짜는 것이라고 볼 수 있습니다.   
그리고 보통 이미 정립되어 있는 방식(알고리즘)을 공부하여 써먹게 됩니다.   
<br/>

***
그런데 작업의 '효율(성능)'은 기준에 따라 이야기가 달라지고 또 기준에는 여러가지가 있습니다.   
컴퓨터 작업에 있어서 효율의 기준은 보통 '(계산)시간'과 "필요공간(메모리)"인데,   
보통은 '시간'을 더 중요시 여깁니다. (특히 기술발전 덕에 메모리가 넉넉해지기도 했구요)   

그리고 이런 알고리즘의 시간을 측정하여 표기하는 대표적인 방법으로 빅오(O) 표기법이 있습니다.   

<br/>

## 2. 알고리즘 시간복잡도과 빅오(O) 표기법
시간복잡도는 입력값과 연산시간의 상관관계 척도로서 알고리즘 성능분석의 주요 방법 중 하나입니다.

기준이 되는 시간은 실제 컴퓨터의 계산 시간으로 하는 경우 컴퓨터 성능에 따라 달라지기에 곤란합니다.
그래서 계산의 기본단위(스탭)이 계산 종료까지 몇 회 실행 되는지를 기준으로 삼게 됩니다.   

예를 들어 어떤 n개의 숫자배열을 정렬하는 작업에서 '선택정렬'(추후 포스팅)이란 알고리즘을 사용할 때,   
최솟값을 '찾아' 가장 왼편에 두는 스탭이 1라운드에 n번 2라운드에 n-1번... n-1라운드에 실행 되어,   
총 (n(n+1)) / 2회의 스탭이 실행됩니다.   

이 때, 라운드는 한 번의 동작이 시작해서 끝날 때까지(위에서는 최솟값을 찾아 옮기는 데까지)를 말하며,   
이런 알고리즘은 측정은 배치에 따라 빨리 끝나는 등의 경우는 무시하고 최대 경우의 수를 따지게 됩니다.   

그런데 당연한 이야기로 이 스탭 수에 따른 실제 계산시간은 또한 입력 값인 n에 따라 크게 변하게 되며,   
숫자가 커질수록 (10에서 10000, 또 100000000~) 될수록 가장 유의미한 변화를 주는 부분은 n^2입니다.   

<br/>

***
빅오(O)는 입력값이 무한해질 때 함수상한을 설명하기 위한 수학 기호로 중요한 항목 이외를 무시합니다.   
여기서 중요항목은 위의 n^2과 같은 부분으로 그 밖에 무시되는 부분은 로그의 밑과 같은 부분들입니다.    

빅오표기에 의한 시간복잡도 크기 비교는 다음과 같습니다.
```
O(1) < O(log n) < O(n) < O(n log n) < O(n^2) < O(2^n) < O(n!)
```   
<br/>
어떤 입력값에도 일정 시간의 결과를 보이는 상수시간(O(1))부터 조금 입력값이 커져도 기하급수적으로   
성능이 떨어지는 완전탐색(브루트포스 O(n!))까지 각 시간복잡도에 해당하는 여러 알고리즘이 있으며,   
보통 O(n^2)의 시간복잡도를 가지는 케이스부터 비효율적인 편인 경우가 많습니다. 

<br/>

마침 [노마드 코더](https://www.youtube.com/watch?v=9TyyMtlk5i4)님께서 알고리즘 자료구조 영상을 만드시는거 같네요. 나중에 참조해야겠습니다.   
언제나 읽어주셔서 감사합니다.^^  

***

```
개인 공부용 블로그입니다.
잘못된 부분에 언제든지 댓글이나 메일로 지적해주시면 감사하겠습니다.
```
