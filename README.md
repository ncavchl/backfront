# backfront

## 인프런 - React + API Server 프로젝트 개발과 배포 (CI/CD) <Br/>

https://www.inflearn.com/course/%EB%A6%AC%EC%95%A1%ED%8A%B8-api-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8#reviews

### nvm 설치 및 사용법

https://dev-yakuza.posstree.com/ko/environment/nvm/

### express 기반 API 서버 생성

### express 명령 설치

npm install --global express-generator

### 프로젝트 폴더 생성

cd ~/git/backfront
express backend -e
cd backend
npm install

### nodemon 개발시 코드가 변하면 자동으로 서버를 재시작해 주는 도구

### swagger, jsdoc 설치

npm install -S swagger-ui-express swagger-jsdoc

app.js 하단에 추가
```node
var app = express();

const swaggerUi = require("swagger-ui-express");
const swaggerJsdoc = require("swagger-jsdoc");
const options = {
  definition: {
    openapi: "3.0.0",
    info: {
      title: "Hello World",
      version: "1.0.0",
    },
  },
  apis: ["./routes/*.js"], // files containing annotations as above
};
const openapiSpec = swaggerJsdoc(options);
app.use("/api-docs", swaggerUi.serve, swaggerUi.setup(openapiSpec));
```
