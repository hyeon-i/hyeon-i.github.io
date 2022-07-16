
## [Mysql] Json데이터 다루는 방법

## 데이터 가져오기
데이터 SELECT해올 때 json데이터에서 특정한 값만 추출
```
SELECT meta, IFNULL(CAST(meta->>"$.attributes[2].value" AS CHAR(10)), 0) AS grade 
FROM {테이블명} WHERE {조건절};
```
- IFNULL: null이면 0을 넣어주도록 함
- CAST(v as type): v값의 타입을 CHAR(10)으로 변환 
- meta->>"$.attributes[1].value  
meta데이터 형태: {attribute: [{key: 키1, value: 값1}, {key: 키2, value: 값2} ... ]}
meta데이터 attribute의 index=1인 데이터의 value값을 가져온다. => 값2


### 참고 하면 좋은 사이트
- [MySQL 에서 JSON Data사용하기](https://www.lesstif.com/dbms/mysql-json-data-54952420.html)
