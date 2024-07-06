<template>
  <h2> App.vue문서</h2>
  <img src="./assets/images/a1.png" width="300" height="150">
  
  <p></p>
  
  안내문 : {{ info }}<br>
  카운트 : {{ count }}<p></p>

  <button @click="suIncrement">증가1</button>
  <button @click="suDecrement">감소1</button> &nbsp;
<!-- 
  <button v-on:click="suIncrement">증가2</button>
  <button v-on:click="suDecrement">감소2</button> &nbsp; -->

  <hr color="blue" size="3" />

  <div v-for = "(item, index) in guest" :key = "index" >
    번호 : {{ index }}, 이름 : {{ item.name }}, 나이 : {{ item.age }}, 제목 : {{  item.title }} <hr>
  </div>
</template>

<script>
//import Hello from './components/HelloWorld.vue'

export default {
  name: 'App',
  //components: { Hello }
  data() {
    return {
      count : 2300,
      info : "안내문",
      guest : [
        { name : "kim", age : 23, title : "sunday" },
        { name : "lee", age : 31, title : "monday" },
        { name : "goo", age : 27, title : "friday" }
      ]
    }
  },
  methods : {
    suIncrement() {
      this.count = this.count + 1;
      this.info  = this.count + ' 숫자를 증가합니다.';
    },
    suDecrement() {
      this.count = this.count - 1;
      this.info  = this.count + ' 숫자를 감소합니다.';
    }
  }
}
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
