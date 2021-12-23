# ** WEBPACK **
- install : npm i -D webpack webpack-cli webpack-dev-server@next
- json 수정
```json
"scripts": {
    "dev": "webpack-dev-server --mode development",
    "build": "webpack --mode production"
  }
```
- parcel은 세 개가 자동화
- webpack-dev-server을 통해 개발 특화 환경을 구성.
- mode는 개발, 제품 모드를 선택할 수 있음
---
## webpack config
- root에 webpack.config.js 파일을 제공해주어야 함.
---
## 개발 서버 오픈 html-webpack-plugin
- install : npm i -D html-webpack-plugin
---
## copy-webpack-plugin
- install : npm i -D copy-webpack-plugin
- webpack.config.js 수정
---
## css-loader, style-loader
- install : npm i -D css-loader style-loader
- webpack.config.js 에 module 추가

- css-loader: css파일을 해석하는 용도
- style-loader: html의 태그 부분에 해석된 부분을 삽입해준다.
- 순서는 style-loader -> css-loader 순서로.
---

## sass-loader, sass
- install : npm i -D sass-loader sass
- webpack.config.js에 module에 sass-loader 추가.
---
## postcss, autoprefixer@9, postcss-loader
- install : npm i -D postcss autoprefixer@9 postcss-loader
- package.json 에 browserslist 추가
- .postcssrc.js 파일 추가 autoprefixer 플러그인 추가
---

## babel 추가
- install : npm i -D @babel/core @babel/preset-env @babel/plugin-transform-runtime
- .babelrc.js 추가
```js
module.exports = {
  presets: ['@babel/preset-env'],
  plugins: [
    ['@babel/plugin-transfrom-runtime']
  ]
}
```
- webpack.config.js에 rules 추가
- babel-loader 추가로 설치하면 Babel 구성 끝
- npm i -D babel-loader
--- 


# Vue
- install : npm i vue@next
- 일반 브라우저 환경에서도 사용하기에 -D X
- src 폴더 만들고 main.js 넣고 App.vue 파일 생성
- webpack.config.js에 main.js 경로 수정

## Vue-loader , Vue-style-loader, @vue/compiler-sfc
- install : npm i -D vue-loader@next vue-style-loader @vue/compiler-sfc
- webpack.config.js 수정


### main.js
- resolve를 통해 import ~ from에 확장자 vue를 붙이지 않더라도 에러처리 나지 않도록 처리할 수 있따.
- webpack.config.js
```js
resolve: {
  extensions: ['.js','.vue']
}
```

### static/images -> src/ 로 이동
### 폴더명 assets로 변경
---
## file-loader
- install : file-loader
- 특정 파일을 읽어서 로드해 줄 수 있는 모듈.
- rules 추가


## ESlint
- install : npm i -D eslint eslint-plugin-vue babel-eslint
- root에 새파일 .eslintrc.js

---


# Vue 문법
- html 태그 안에 @click="함수명"  <해당 태그 클릭시 실행>
- 태그 안에 v-if="조건식"
- v-for="fruit in fruits" :key="fruit" :name="fruit" {{ fruit }}


# Vue 라이프사이클 훅

![LifeCircle](https://v3.ko.vuejs.org/images/lifecycle.svg)

- created
- mounted