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
---
###
- 리스트중에 조합을 전부다 알려줌( 순서 상관 X, 즉 AB와 BA를 같이봄)
- EX) [1,2,3]  = > [12] [13] [23]
```
from itertools import combinations

array= [1,2,3]
for i in combinations(array, 2):
    print(i)  #(1,2)(1,3)(2,3)
```
---


- 반시계 방향으로 돌기
  
```
((dr+3)%4,(dr+2)%4,(dr+1)%4,dr)

```
