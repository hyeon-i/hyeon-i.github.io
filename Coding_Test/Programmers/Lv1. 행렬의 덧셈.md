## [문제]
### 문제 사이트  
https://school.programmers.co.kr/learn/courses/30/lessons/12950

### 문제 설명
행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은 행, 같은 열의 값을 서로 더한 결과가 됩니다. 2개의 행렬 arr1과 arr2를 입력받아, 행렬 덧셈의 결과를 반환하는 함수, solution을 완성해주세요.

### 제한 조건
행렬 arr1, arr2의 행과 열의 길이는 500을 넘지 않습니다.

### 입출력 예
|arr|arr2|return|
|---|---|---|
| [[1,2],[2,3]] | [[3,4],[5,6]] | [[4,6],[7,9]] |
| [[1],[2]] | [[3],[4] | [[4],[6]] |

---
## [풀이]
**나의 풀이**
```python
[python]
import numpy as np

def solution(arr1, arr2):
    answer = np.array(arr1) + np.array(arr2)
    return answer.tolist()
```

**다른 풀이**  
```python
[python]
def solution(arr1, arr2):
    return [[ c+d for c, d in zip(a, b)] for a , b in zip(arr1, arr2)]
```
참고: [블로그-파이썬의 zip() 내장 함수로 데이터 엮기](https://www.daleseo.com/python-zip/)

**나의 풀이**
```javascript
[javascript]

function solution(arr1, arr2) {
    var answer = [];
    
    arr1.forEach((row, r)=>{
        let row_sum = []
        row.forEach((el, c)=>{
            row_sum.push(el + arr2[r][c])
        })
        answer.push(row_sum)
    });
    return answer;
}
```

**다른 풀이**
```javascript
[javascript]

function solution(arr1, arr2) {
    return arr1.map((a1, i)=> a1.map((a,j)=> a + arr2[i][j]));
}
```
forEach를 map형식으로 바꿔놓은 형태