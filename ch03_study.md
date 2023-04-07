## 쉽게 배우는 자료구조 with 파이썬, CH03 연습 문제 풀이


#### 1. 다음 주장의 참/거짓을 말하시오.
(A)
```
1. 참
2. 거짓 / n = Ω(n)
3. 참
4. 참 (되긴한다. 교집합이므로)
5. 참
6. 참
7. 참
8. 참
9.참
10. 거짓 / 7n-3 = Θ(n)
```
***
#### 2. 입력의 크기가 n일때 다음 알고리즘의 수행 시간은 n에 관한 어떤 차수에 비례하는가? 

```
sample(A[], n):
    sum <- 0
    for i <- 0 to n-1:
        sum <- sum + A[i]
    return sum
```
(A)
```
재귀 함수가 아니므로 n 에 비례한다.
```
***
#### 3. 입력의 크기가 n일때 다음 알고리즘의 수행 시간을 빅오,오메가,쎄타 표기법으로 작성하시오. 

```
sample(A[], n):
    sum <- 0
    for i <- 0 to n-1:
        for j <- 0 to n-1:
            sum <- sum + A[i] * A[j]
        return sum
```
(A)
```
O(n^2), Ω(n^2), Θ(n^2)
```
***
#### 4. 입력의 크기가 n일 때 다음 알고리즘의 수행 시간을 쎄타 표기법으로 나타네시오.
```
matixMult(A[][], B[][], M[][], n):
    for i <- 1 to n:
        for j <- 1 to n:
            M[i,j] <- 0
            for k <- 1 to n:
                M[i,j] <- M[i,j] + A[i,k]*B[k,j]
```

(A)
```
for i 에서 n
for j 에서 n => n^2
for k 에서 n => n^3 + n^2
따라서 Θ(n^3)
```

***
#### 5. 입력의 크기가 n일 때 다음 알고리즘의 점근적 수행 시간을 빅오, 오메가 표기법으로 나타내라.
```
sample(A[], n):
    for i <- 1 to n:
        if (random(1, 100) <= 50):
            sum <- 0
            for i <- 1 to n:
                sum <- sum + A[i]
```
(A)
```
random 함수가 모두 50 이하일 경우, O(n^2)
random 함수가 모두 50 초과일 경우 Ω(n)
```

***
#### 6. 입력의 크기가 n일 때 다음 알고리즘의 점근적 수행 시간을 빅오, 오메가 표기법으로 나타내시오.
```
sample(A[], n):
    if (n=1) return 1
    else if (random(1, 100) <= 50): 
        sum <- 0       
        for i <- 1 to n:
            sum <- sum + A[i]    
    sample(A, n-1)
```
(A)
```
random 함수가 모두 50 이하일 경우, O(n^2)
random 함수가 모두 50 초과일 경우 Ω(n)
```
***
#### 7. 입력의 크기가 n일 때 다음 알고리즘의 점근적 수행 시간은?
```
sample(A[], n):
    if(n=1) return 1
    sum <- 0
    for i <- 1 to n:
        sum <- sum + A[i]
    tmp <- sum + sample(A, n-1)
    return tmp
```
(A)
```
재귀형 n + n-1 + n-2 .... 2 + 1 수행한다.
즉, 점근적 하한으로  (n^2+n)/2 이므로, Θ(n^2)
```
