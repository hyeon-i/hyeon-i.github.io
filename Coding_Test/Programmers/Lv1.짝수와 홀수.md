## [문제]
### 문제 사이트  
https://school.programmers.co.kr/learn/courses/30/lessons/12937

### 문제 설명
정수 num이 짝수일 경우 "Even"을 반환하고 홀수인 경우 "Odd"를 반환하는 함수, solution을 완성해주세요.

### 제한 조건
- num은 int 범위의 정수입니다.
- 0은 짝수입니다.

### 입출력 예
|arr|return|
|---|---|
|3|"Odd"|
|4|"Even"|

---
## [풀이]
**나의 풀이**
```python
[python]

def solution(num):
    return '짝수' if num % 2 == 0 else '홀수'
```

**다른 풀이**
```python
[python]

def solution(num):
    return ["Even", "Odd"][num & 1]
```
비트연산자를 이용하여 해결 [[참고]](https://codechacha.com/ko/python-difference-and-ampersand/)  

**나의 풀이**
```javascript
[javascript]

function solution(num) {
    return num%2==0? "Even" : "Odd";
}
```