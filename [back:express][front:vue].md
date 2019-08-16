backend는 express 그리고 front는 Vue를 사용한다.

시나리오
node 스터디를 진행 중이다. 한 달이 지났지만, 아직 제대로된 CRUD 애플리케이션 하나 만들지 못했다.
express와 vue를 합치는데 있어서 가장 궁금한 점은 express와 vue가 어떻게 데이터를 서로 주고받을 지에 대한 의문이었다. 거디다가 몽고디비도 사용해야 하니
정말 모르겠었다. 당연히 Webpack이나 Vue-cli 같은 것도 전혀 알지 못했다.

## * vue에서 vue-cli와 webpack의 차이는 뭔가?
* webpack
  * vue-loader?
    >  ```vue-loader```는 파일을 파싱하고 각 language block을 추출하며 필요한 경우 다른 로더를 통해 파이프 처리한 후 마지막으로           Module.exports가 Vue.js 컴포넌트 엘리먼트 옵션 객체인 CommonJS 모듈로 다시 조합한다. - 한마디로 알 수없다.
    
```*.vue``` 파일은 HTML과 같은 문법을 사용한다.
구조는 language block인 ```<template>```,```<script>```,```<style>```로 이루어진다.

```<template>```
* 기본 html
* ```<template>```는 ```*.vue```파일에 최대 1개다.

    
