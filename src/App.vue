<template>
  <h1>Hello {{ animal }}</h1>
  <h2>원숭이는 {{ food }}를 좋아합니다.</h2>
  <!-- vue directive : 태그 안에 속성처럼 쓰는 것-->
  <!-- v-text : 많이 안 씀-->
  <h3 v-text="food"></h3>
  <input type="text" v-model="food"/><!--상태관리가 가능-->
  <a :href="food">{{food}}</a>
  <div>{{alertMessage}}</div>
  <div v-html="alertMessage"></div><!-- v-html은 확실한 경우에만 사용하기.-->
  <!-- v-bind를 사용시 imageSource를 변수처럼 사용할 수 있다. 동적으로 이미지를 연결할 때 사용. 
      url에서도 사용가능
      v-bind생략하고 :만 사용가능.
  -->
  <img v-bind:src="imageSource" alt="random"/> 
  <a :href="naverUrl">naver</a>
  <hr/>

  <!-- 동적으로 클래스를 부여 1.배열, 2. 오브젝트-->
  <!-- 오브젝트 형식 { 키(클래스): 값(참/거짓 조건)} -->
  <!-- -가 들어간 클래스는 인지하지 못 하니 ""로 묶어주기 -->
  <h2 v-bind:class="{ red: food==='apple', 'not-good' : food==='rice'}">원숭이는 {{food}}를 좋아합니다.</h2>

</template>

<script>

export default {
  name: 'App',
  //data:()=>{} 사용가능
  data(){
    return{ //key와 value형태로 값을 리턴
      animal: "Monky",
      food:"apple",
      alertMessage: "<h2>경고!!</h2>",
      imageSource:"https://placeimg.com/100/100/any",
      naverUrl:"https://www.naver.com"
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
input {
  font-size: 20px;
}
.orange{
  color:orange;
}
.salmon{
  color:salmon;
}
.red{
  color:red;
}
.not-good{
  text-decoration: line-through;
}
</style>
