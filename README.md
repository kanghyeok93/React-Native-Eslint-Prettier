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
