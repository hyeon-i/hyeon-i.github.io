## Javascript 정렬(Sort())
Javascript에서 배열 정렬은 sort()를 사용하는데 다른 언어들과 사용법이 조금 다르다. 
```
arr.sort([compareFunction])
```
 5 1 10 2 를 정렬한다고 하자. 예상 결과는 1 2 5 10지만, 실제 결과는 1 10 2 5가 나온다.
Docs를 보면 '`기본 정렬 순서는 문자열의 유니코드 코드 포인트를 따른다`'고 되어있다.
숫자가 아닌 유니코드로 비교를 하는 것인데, 10이 2보다 작은 이유는 유니코드 상 1이 2보다 먼저이기 때문이다. 꼭 compareFunction을 넣어주자.

```javascript
// 오름차순(ASC)
array.sort(function(a,b){
	return a - b
})

// 내림차순(DESC)
array.sort(function(a,b){
	return b - a
})
```
### 한 줄로 축약
```javascript
array.sort((a,b)=>a-b);
```
### 객체 정렬
```javascript
let objs = [
    {id:55, name:'Kim'},
    {id:23, name:'Yeon'},
    {id:31, name:'Jeong'}
]
objs.sort((a,b)=> a.id - b.id) // asc
console.log(obj);
```
결과 
```
[
  { id: 23, name: 'Yeon' },
  { id: 31, name: 'Jeong' },
  { id: 55, name: 'Kim' }
]
```
### 참고사이트
- [Javascript Docs = Sort()](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
- [블로그 - 배열 정렬하기 (오름차순, 내림차순, 문자열, 객체)](https://hianna.tistory.com/409)