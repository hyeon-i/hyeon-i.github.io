## [문제]
### 문제 사이트  
https://school.programmers.co.kr/learn/courses/30/lessons/12977?language=javascript

### 문제 설명
주어진 숫자 중 3개의 수를 더했을 때 소수가 되는 경우의 개수를 구하려고 합니다. 숫자들이 들어있는 배열 nums가 매개변수로 주어질 때, nums에 있는 숫자들 중 서로 다른 3개를 골라 더했을 때 소수가 되는 경우의 개수를 return 하도록 solution 함수를 완성해주세요.

### 제한 조건
- nums에 들어있는 숫자의 개수는 3개 이상 50개 이하입니다.
- nums의 각 원소는 1 이상 1,000 이하의 자연수이며, 중복된 숫자가 들어있지 않습니다.

### 입출력 예
|arr|return|
|---|---|
|[1,2,3,4]|1|
|[1,2,7,6,4]|4|

**입출력 예 설명**  
**입출력 예 #1**   
[1,2,4]를 이용해서 7을 만들 수 있습니다.

**입출력 예 #2**  
[1,2,4]를 이용해서 7을 만들 수 있습니다.  
[1,4,6]을 이용해서 11을 만들 수 있습니다.  
[2,4,7]을 이용해서 13을 만들 수 있습니다.  
[4,6,7]을 이용해서 17을 만들 수 있습니다.  

---

## [풀이]
소수는 1과 자기 자신으로만 나누어 떨어지는 양의 정수  
2,3,5,7,11,13,17, ... ,111, ..  

(1) 경우의 수를 이용하여 숫자 구하기  
(2) 숫자 중 소수 구하기 

**나의 풀이**
```python
[python]

from itertools import combinations

def solution(arr):
    count = 0
    for case in list(combinations(arr, 3)):
        if isPrime(sum(case)):
            count += 1
    return count

def isPrime(num):
    for i in range(2,num):
        if num % i == 0:
            return False
    return True
```
배열의 조합:  
- [블로그-파이썬 (Python)에서 리스트에 있는 값들의 모든 조합을 구하기](https://ourcstory.tistory.com/414)  
- [Python Docs](https://docs.python.org/ko/3/library/itertools.html)

**나의 풀이**
```javascript
[javascript]

function solution(nums) {
    let count=0;
    for(let i=0; i<nums.length-2; i++){
        for(let j=i+1; j<nums.length-1; j++){
            for(let k=j+1; k<nums.length; k++){
                if(isPrime(nums[i]+nums[j]+nums[k]))
                    count++
            }
        }
    }
    return count;
}

const isPrime = (num)=>{
    for(i=2; i<=Math.sqrt(num); i++){
        if(num%i == 0) return false
    }
    return true;
}
```