# react-native eslint & prettier 설정 (with airbnb-style)

eslint에도 code formatting rule이 있어, prettier와 conflict이 나기 때문에 추가적인 설정을 해주어야 한다.

eslint와 prettier를 같이 사용하기 위해서는 다음 두 가지 module을 설치하고 설정해줘야한다.

- eslint-plugin-prettier   
prettier를 ESLint 플러그인으로 추가한다. 즉, prettier에서 인식하는 코드상의 포맷 오류를 ESLint 오류로 출력해준다.

- eslint-config-prettier  
eslint의 code-formatting rule을 모두 꺼서 conflict 방지

```
npm install --save-dev eslint-plugin-prettier
```
```
npm install --save-dev eslint-config-prettier
```  
\
airbnb eslint 설정과 react-native-community eslint 관련 모듈설치
```
npx install-peerdeps --dev eslint-config-airbnb
```
```
npm install --save-dev @react-native-community/eslint-config
```
\
.eslintrc.json 파일의 extends 키에 다음과 같이 적어준다.

```js
"extends": [
    "eslint:recommended",
    "@react-native-community",
    "airbnb",
    "airbnb/hooks",
    "plugin:prettier/recommended"
],
```
\
IntelliJ툴 사용 시 설정창(⌘ + ,)에서 On save 체크박스 체크 후 적용할 시 코드 작성 중간중간 저장하면서 동시에 prettier를 할 수 있다.  
(단축키 설정에 따라 ⌘S가 아닐 수 있음)
![스크린샷 2021-06-30 오후 8 22 30](https://user-images.githubusercontent.com/38206489/123952717-59a84100-d9e1-11eb-8f14-6cb34c4cd329.png)

## CLI 사용법

eslint 자동수정은 아래명령어로 진행
```
eslint . --fix
```

prettier 자동수정은 아래 명령어로 진행
```
prettier --write "**/*.js"
```
