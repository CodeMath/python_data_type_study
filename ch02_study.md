## 쉽게 배우는 자료구조 with 파이썬, CH02 연습 문제 풀이


#### 1. 다음 수열의 n번째 항을 구하는 재귀 알고리즘을 작성하시오.
```a_n = 5a_{n-1} + 3, a_1=0```

(A)
```
Prd(n):
    if(n = 1):
        return 0
    else:
        return 5Prd(n-1) + 3
```
***

#### 2. 본문에서 소개한 다음 알고리즘에서 양의 정수 n 에 대해 함수 seq()는 총 몇회 호출되는가? 이떄 최초의 호출 seq(n)도 포함하여 센다.
```
seq(n):
    if(n=1) return 1
    else return seq(n-1) +3
```

(A)
```
n=2 일 때, seq(2) = seq(1) + 3, seq(1) = 1
n=3 일 떄, seq(3) = seq(2) + 3, seq(2) = seq(1)+3, seq(1)=1
n=k 일 때, seq(k) = seq(k-1) + 3, seq(k-2) = seq(k-3)+3... seq(1)=1

따라서 n 번 호출된다.
```
***
#### 3. 다음 피보나치 수열을 구하는 재귀 알고리즘에서 5번째 피보나치 수를 구하는 fib(5)를 수행하면 함수 fib()는 총 몇 회 호출되는가? 이때 최초의 호출 fib(5)도 포함해 센다.

```
fib(n):
    if (n=1 or n=2) return 1
    else return fib(n-1) + fib(n-2)
```

(A)
```
fib(5) > fib(4) + fib(3) 
       > fib(3) + fib(2) + fib(2) + fib(1)
       > fib(2) + fib(1)
총 9번  
``` 
***
#### 4. 하노이탑 재귀 알고리즘, 5개의 원반 옮기기 move(5, a, b, c)를 수행. 이때 move는 총 몇 회 호출되는가? 
```
move(n, a, b, c):
    if(n>0):
        move(n-1, a, c, b)
        a에 있는 원반을 b로 옮긴다.
        move(n-1, c, b, a)
```

(A)
```
n개 원반 당, move 2번, 원반 1번 이동한다.
즉, move(n) = 2 * move(n-1) 이므로, M(n) = Sum(2^n)  
M(5) = 2^5 - 1 = 31번
```
***

#### 5. 4번 문제에서 함수 move()의 호출 함수 대신 원반을 옮기는 행위에 대한 총 횟수는? 이 횟수의 move()의 호출 횟수는 어떤 관계인가?
(A)
```
원반은 함수 호출 당 1번 시행된다.
move 함수가 2^n -1 번 시행될 경우 원반 또한 1번씩 되므로, 5번 시행되면
> 31번 시행된다.  
```

***

#### 6. 4번 문제에서 다음처럼 경계 조건이 빠진 채 알고리즘이 수행되면 어떻게 되는가?
```
move(n, a, b, c):
    move(n-1, a, c, b)
    a에있는 원반을 b로 옮긴다.
    move(n-1, c, b, a)   
```

(A)
```
n이 1이 될 경우,
move(0, a, c, b)를 시행해야한다. 하지만 원판이 0개인 경우 0번 이동되어 종료되어야하지만,
필터링이 되지 않아 무한 반복시행이 될 수 있다.
move(0, a, c, b) -> move(-1, a, c, b) -> move(-2, a, c, b)....

```

***

#### 7. 선택 정렬 알고리즘에서 임의의 양의 정수 n에 대해 selectionSort(A, n)을 수행하면 함수 selectionSort()는 총 몇 회 수행되는가? 최초 호출 포함해서. 
```
selectionSort(A[], n):
    if(n>1):
        A[0....n-1] 중 가장 큰 수 A[k] 찾기
        A[k] <-> A[n-1]
        selection(A, n-1) 
```

(A)
```
첫 번째로 n개 원소중 가장 큰 원소 A[k]를 찾은다음 A[k]와 A[n-1] 비교해 큰 수를 마지막 배열에 저장한다.
따라서 가장 마지막 원소는 n개 중 가장 큰 원소가 된다.
n개의 원소를 selectionSort 해야하므로 n번 시행한다. 
```

***

#### 8. 다음의 재귀적 표현해서 <T> 는 무엇을 표현하는가?
```
<T> = <숫자> | <T><숫자>
<숫자> = 0 | 1 | .... | 9
```

(A)
```
10진수.
```