## 노드몬 (Nodemon())
평소에 node 서버를 껐다 켰다 해야해서 불편했는데 이번에 노드몬이라는 툴을 알게됐다. pm2(watch 옵션으로 실행)와 같이 노드몬도 파일 변경이 있으면 서버를 재시작해주는 역할을 한다. 약간의 간단한 세팅이 필요하다.  
  
### 1. 노드몬 설치
```
npm install nodemon --save-dev
```
- --save-dev : 개발용으로 설치  

### 2. pakage.json 설정
pakage.json를 들어가보면 devDependencies에 nodemon이 추가된 것을 볼 수 있다. 
```
[pakage.json]

"devDependencies": {
    "nodemon": "^2.0.19"
  }
```
보통은 main에 메인이되는 index.js이 입력된다.
- "실행 이름": "nodemon main"  // main의 index.js를 실행
```
[pakage.json]

...
"main": "index.js",
  "scripts": {
    "server": "nodemon main" ,
  },
...
```
### 3. 실행
```
npm run server
```

만약 프로젝트 내 start가 아래처럼 지정이 되어있다면 
```
[pakage.json]

"main": "index.js",
  "scripts": {
    "server": "nodemon main" ,
    "start": "node ./bin/www"
  },
```
```
npm run start nodemon server.js
```

### 4. 중지
```
ctrl + c
```

### 참고 사이트
- [블로그: BoilerPlate Code 04 - 노드몬(NODEMON)](https://velog.io/@gparkkii/NodejsNODEMON)
- [블로그: nodemon 노드몬 설치 사용방법 ](https://dubaiyu.tistory.com/191)