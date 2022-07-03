## [문제]
### 문제 사이트  
https://programmers.co.kr/learn/courses/30/lessons/12922

### 문제 설명
길이가 n이고, "수박수박수박수...."와 같은 패턴을 유지하는 문자열을 리턴하는 함수, solution을 완성하세요. 예를들어 n이 4이면 "수박수박"을 리턴하고 3이라면 "수박수"를 리턴하면 됩니다.

### 제한 조건
n은 길이 10,000이하인 자연수입니다.

### 입출력 예
|arr|return|
|---|---|
|3|"수박수"|
|4|"수박수박"|

---
## [풀이]
**나의 풀이**
```python
[python]

def solution(n):
    answer = ''
    for i in range(n):
        answer += '수' if i%2 == 0 else '박'
    return answer

```
**파이썬 삼항 연산자**  
`결과 = A if 조건 else B if 조건 else C`  [[참고]](https://info-lab.tistory.com/303)  

**다른 풀이**
```python
[python]

def solution(n):
    answer = "수박" * n
    return answer[:n]
```

**나의 풀이**
```javascript
[javascript]
function solution(n) {
    let str = '수박'.repeat(n/2);
    return  n%2 == 1? str+'수' : str;
}
```
**다른 풀이**
```javascript
[javascript]

def solution(n):
    return '수박'.repeat(n).substring(0,n);
```