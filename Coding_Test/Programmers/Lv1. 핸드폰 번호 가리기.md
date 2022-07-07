## [문제]
### 문제 사이트
https://school.programmers.co.kr/learn/courses/30/lessons/12948

### 문제 설명
프로그래머스 모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다.
전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 *으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.

### 제한 조건
phone_number는 길이 4 이상, 20이하인 문자열입니다.

### 입출력 예
|phone_number|return|
|----------|---------|
|"01033334444"|"*******4444"|
|"027778888"|"*****8888"|

---
## [풀이]
### 나의 풀이
```python
[python]
def solution(phone):
    return ('*'*(len(phone)-4))+phone[-4:]
```
```javascript
[javascript]
function solution(phone) {
    phone = phone.split('')
    for(let i=0; i<phone.length-4; i++){
        phone[i]="*"
    }
    return (phone.join('')); 
}
```
### 다른 사용자 풀이
```javascript
[javascript]
// 정규식
function solution(phone_number) {
    return phone_number.replace(/\d(?=\d{4})/g,'*');
}

// repeat
function solution(phone_number) {
    return "*".repeat(phone_number.length-4)+phone_number.slice(-4);
}

```
**정규식: /\d(?=\d{4})/g**  
\d: 0~9 사이 숫자 중 하나 [0-9]  
숫자(\d) 중에 4자리 숫자(\d{4})가 뒤 따라오는 형태, \d{4}는 대응되지 않음  
[정규식 참고]  
- [공식 사이트](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Regular_Expressions) 
 : 어서션에 정리되어 있음  
- [블로그](https://bingbingba.tistory.com/20)