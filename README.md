a# Vue 문법
- html 태그 안에 @click="함수명"  <해당 태그 클릭시 실행>
- 태그 안에 v-if="조건식"
- v-for="fruit in fruits" :key="fruit" :name="fruit" {{ fruit }}


# Vue 라이프사이클 훅

![LifeCircle](https://v3.ko.vuejs.org/images/lifecycle.svg)

- created
- mounted

## Vue 보간법(Interpolation)
- 문자열 : 데이터 바인딩의 가장 기본 형태는 "Mustache"(이중 중괄호 구문) 기법을 사용한 문자열 보간법(text interpolation)
- v-once 디렉티브를 사용하여 데이터가 변경되어도 갱신되지 않는 일회성 보간을 사용할 수 있다.

## v-html (원시 html)
```vue
<h1 v-html="msg"></h1>
```
- 해당 부분은 원시 html로 인식할 수 있다.

## v-bind
- html 속성에서 사용할 수 없는 부분은 바인드를 통해서 연결할 수 있다.
```vue
// 전체 문법
<h1 v-bind:id="msg"></h1>

//약어
<a :href="url"></a>

// 동적 전달인자와 함께 쓴 약어
<a :[key]="url">
```

## v-on
```vue
<a v-on:click="doSomething></a>

//약어
<a @click="doSomething></a>

//동적 전달인자와 함께 쓴 약어
<a @[event]="doSomething"> </a>

```

## Vue computed caching
- 동일한 결과의 함수를 반복할 필요 없이 computed 된 데이터를 사용하면 됨.
- computed 값은 readonly!


## vue getter/setter
- readonly인 computed값은 Getter!
- data값은 둘의 기능 모두 가능.

```vue
computed: {
  reversedMessage: {
    get() {
      return this.msg.split('').reverse().join('')
    },
    set(value) {
      this.msg = value
    }
  }
}
```