# {{project name을 작성해주세요}}

## 프로젝트 개요
{{project name}} 서버 입니다.
간단한 프로젝트 소개와 주요 기능을 설명합니다.


---
## 세팅 및 설치 방법
프로젝트 시작할때는 그 당시 nest 최신버전을 지향합니다.

세팅 및 설치 방법 가이드를 확인 후 프로젝트의 리드미에서 프로젝트를 세팅하기 위해 작성된 가이드는 제거합니다.

### git 세팅
```
git 
1. github에 새로운 repository를 생성한다. 
2. git clone --mirror git@github.com:mcircle-dev/basic-nestjs.git {임시폴더명} 
3. cd {임시폴더명}
4. git remote set-url --push origin {{1번에서 생성한 repository url}}
5. git push --mirror
6. git clone {{1번에서 생성된 repository url}}
```

### nestjs 최신버전 업데이트
```
//step1
npm install -g @nestjs/cli

//step2: nest 최신버전 확인
nest --version

// update deependencies
npm i -g npm-check-updates

//step: 3 update package하기 
ncu -u -f /^@nestjs/ 

```
###  app 구동 방법 꼭 해당 프로젝트에 맞게 세팅!
### prerequisite comment 삭제 및 버전 정보 입력!

---

### prerequisite
_node버전은 프로젝트 생성시 배포할 서버에서 지원하는 가장 최신 LTS 버전으로 사용합니다.
DB는 rdb는 mariaDB를 사용하고 nosql은 mongodb(documentDB)를 사용합니다._


| 항목                    | version | 
|-----------------------|:-------:|
| Node                  | 20.11.0 |
| mariaDB               |         |



### Installation, Build

```bash
# install
$ npm install

# build
$ npm run build
```

### Running the app

```bash
# local 환경 실행
$ npm run start:local

# dev 환경 실행
$ pm2 start {{ecosystem.config.js 내부의 name}}

# docker 환경 실행
$ docker
``` 

### Test

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e
```
---

### 횐경 변수 관리방법
|     환경변수     | local | dev | qa  | prod | 
|:------------:|:-----:|:---:|:---:|:----:|
|     .env     |   O   |  O  |     |      |
| SecretManger |       |     |  O  |  O   |
참고 : [세팅 가이드](https://well-check.atlassian.net/wiki/spaces/QPKY/pages/917110829/env), [env 파일 확인](https://well-check.atlassian.net/wiki/spaces/UxzsMGJ2xrp3/pages/985268300)


### 서버 구성 정보
|          | local |  dev  | qa  | prod | 
|:--------:|:-----:|:-----:|:---:|:----:|
| ci/cd 여부 |   X   |   X   |  O  |  O   |
|    환경    |       |  ec2  | ec2 | ecs  |


---
### ESLint와 Prettier 설정
- [ESLint와 Prettier  가이드 보기](https://well-check.atlassian.net/wiki/spaces/QPKY/pages/917176350/eslint+prettier)


### REST API 명명 규칙
- [REST API 명명 규칙 자세히 보기](https://well-check.atlassian.net/wiki/spaces/QPKY/pages/921763841/rest+api+naming+rule)


### request, response 포맷
- [요청 및 응답 포맷 가이드 보기](https://well-check.atlassian.net/wiki/spaces/QPKY/pages/680230913/request+response)


### 기본 idsTrust nestjs 프로젝트 구조

```plaintext
├── src
│   ├── app.controller.ts
│   ├── app.module.ts
│   ├── app.service.ts
│   ├── main.ts
│   │── common
│   │    ├── constants 
│   │    ├── decorator 
│   │    ├── enum
│   │    ├── filter
│   │    └── interceptor
│   └── libs
│       ├── aws
│       └── log
├── test
├── .prettierrc
├── jest-unit.config.js
├── nest-cli.json
├── package.json
├── package-lock.json
├── README.md
├── tsconfig.build.json
└── tsconfig.json
