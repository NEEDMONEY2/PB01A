# python 문법, 활용

### 

- 정렬된 순서를 유지하면서 배열 a에 x를 삽입할때 가장 왼쪽 or 오른쪽 인덱스를 반환
  
```
from bisect import bisect_left, bisect_right

a = [1,2,3,3,5,6,7]
x= 3

print(bisect_left(a,x))  # 2
print(bisect_right(a,x)) # 4

```

###
- 리스트중에 조합을 전부다 알려줌( 순서 상관 X, 즉 AB와 BA를 같이봄)
- EX) [1,2,3]  = > [12] [13] [23]
```
from itertools import permutations  # 중복포함
from itertools import combinations  # 중복없음

array= [1,2,3]
for i in combinations(array, 2):
    print(i)  #(1,2)(1,3)(2,3)

////////////////////////////////////

# 재귀로 구현해보기
# 조합
def gen_combinations(arr, n):
    result = []
    if n == 0:
        return [[]]
    for i in range(0, len(arr)):
        elem = arr[i]
        rest_arr = arr[i + 1:]
        for C in gen_combinations(rest_arr, n - 1):
            result.append([elem] + C)
    return result

# 수열
def gen_permutations(arr, n):
    result = []

    if n == 0:
        return [[]]

    for i, elem in enumerate(arr):
        for P in gen_permutations(arr[:i] + arr[i + 1:], n - 1):
            result += [[elem] + P]
    return result

```


- 반시계 방향으로 돌기
  
```
for i in ((dr+3)%4,(dr+2)%4,(dr+1)%4,dr)

```




- 소수 찾기 (feat.에라토스테네스의 체)
  
```
import math

n = 1000000
arr = [True for i in range(n+1)]

for i in range(2,int(math.sqrt(n))+1):
    if arr[i] ==True:
        j = 2
        while i * j <=n:
            arr[i*j] = False
            j += 1

for i in range(2, n+1):
    if arr[i]:
        print(i, end =' ')
```

- 2차원 리스트에서 index찾기 
  
```
for i, row in enumerate(arr):
    for j, col in enumerate(row):
       if col == "찾고자 하는 값":
           print(i,j)
```

- 최대공약수와 최대공배수 구하기
```
# 최대공배수
for j in range(min(a,b),0,-1):
    if a % j == 0 and b % j == 0:
        gcm = j
        break

# 최소공배수
for i in range(max(a,b),(a*b)+1):
    if i % a == 0 and i % b == 0:
        lcm = i
        break
```
