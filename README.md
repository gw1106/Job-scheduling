# Job scheduling



## 1. Job scheduling 문제

‘작업 스케줄링(Job Scheduling) 문제’는 n개의 작업, 각 작업의 수행 시간 ti, i = 1,2,3,…,n, 그리고 m개의 동일한 기계가 주어질 때, 모든 작업이 가장 빨리 종료되도록 작업을 기계에 배정하는 문제이다. 단, 한 작업은 배정된 기계에서 연속적으로 수행, 기계는 1번에 하나의 작업만을 수행한다.

작업 스케줄링 문제를 해결하기 위한 가장 간단한 방법은 그리디 알고리즘을 이용하는 것이다.
즉, 배정된 작업이 가장 빨리 끝나는 기계에 새 작업을 배정하는 것이다.



## 2. 알고리즘

Approx_JobScheduling
입력: n개의 작업, 각 작업 수행 시간 ti, i= 1,2,…,n, 기계 Mj, j = 1,2,…,m
출력: 모든 작업이 종료된 시간

```
1. for j = 1 to m		// 초기화
2.   L[j] = 0
3. for i = 1 to n		// n개의 작업을 배정
4.   min = 1		
5.   for j = 2 to m {	
6.     if (L[j]<L[min]){
7.       min = j
8.     }
9.   작업 i를 기계 Mmin에 배정
10.   L[min] = L[min] + ti
11.   }
12. }
13. return 가장 늦은 작업 종료 시간
```



## 3. 시간복잡도

Approx_JobScheduling 알고리즘은 n개의 작업을 하나씩 가장 빨리 끝나는 기계에 배정한다.
이러한 기계를 찾기 위해 for-루프가 (m-1)번 수행된다.
따라서 O(m) 시간 동안 기계의 작업 종료 시간을 살핀다.
또한, n개의 작업을 배정하고, 마지막 line 10에서 배열을 탐색한다.
n*O(m) + O(m) = O(nm)

![https://dudri63.github.io/image/algo38-4.png](https://dudri63.github.io/image/algo38-4.png)

가장 마지막으로 배정된 작업 i가 T부터 수행, OPT’ = T + ti이다.
또한, T’는 작업 i를 제외한 평균 종료 시간이다.
따라서 T <= T’이다.

![https://dudri63.github.io/image/algo38-5.png](https://dudri63.github.io/image/algo38-5.png)



## 4. 알고리즘 실현

이 경우 입력 값은 다음과 같습니다.

* n = [2, 3, 4, 5] (작업의 개수)

* m = 2  (기계의 개수)

* 작업시간은 10초 이내의 랜덤값














## 5.참조 

양성봉, 『알기 쉬운 알고리즘』. 파주: (주)생능출판사, 2013







        
        


