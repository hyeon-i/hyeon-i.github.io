## [문제]
### 문제 사이트
https://school.programmers.co.kr/learn/courses/30/lessons/12934

### 문제 설명
임의의 양의 정수 n에 대해, n이 어떤 양의 정수 x의 제곱인지 아닌지 판단하려 합니다.
n이 양의 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 양의 정수 x의 제곱이 아니라면 -1을 리턴하는 함수를 완성하세요.

### 제한 사항
n은 1이상, 50000000000000 이하인 양의 정수입니다.

### 입출력 예
|n|return|
|---|---|
|121|144|
|3|-1|

***입출력 예 설명**  
**입출력 예#1**
121은 양의 정수 11의 제곱이므로, (11+1)를 제곱한 144를 리턴합니다.

**입출력 예#2**
3은 양의 정수의 제곱이 아니므로, -1을 리턴합니다.

---
## [풀이]
**나의 풀이**
```python
[python]
import math

def solution(n):
    return int(math.pow(math.sqrt(n)+1,2)) if math.sqrt(n) == int(math.sqrt(n)) else -1
```

```python
def solution(n):
    sqrt = n ** (1/2)

    if sqrt % 1 == 0:
        return (sqrt + 1) ** 2
    else: 
        return -1
```

```javascript
function solution(n) {
    let num = Math.sqrt(n);
    return Number.isInteger(num)? (num + 1)**2 : -1;
}
```
정수 판별 방법: Number.isInteger(), % 연산자 [[참고]](https://hianna.tistory.com/463)