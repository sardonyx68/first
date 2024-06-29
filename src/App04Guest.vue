<template>
  <div>

    <img src="./assets/images/main_4.jpg" width="300" height="150">
    <p></p>

    디저트 : {{ kind }}<br>
    안내문 : {{ info }}<br>
    카운트 : {{ count }} <p></p>

    <hr color="blue" size="3" />

    <!-- guest 배열객체 출력  -->
    <div v-for = "(item, index) in guest" :key = "index" >
      번호 : {{ index }}, 이름 : {{ item.name }}, 나이 : {{ item.age }}, 제목 : {{  item.title }} <hr>
    </div>

  </div>
</template>

<script>
//import Hello from './components/HelloWorld.vue'

export default {
  name: 'App',
  //components: { Hello }
  data() {
    return {
      kind : "녹차cake",
      count : 500,
      info : "안내문" ,
      guest : [
        { name : "kim", age : 23, title : "sunday" },
        { name : "lee", age : 31, title : "monday" },
        { name : "goo", age : 27, title : "friday" }
      ]
    }
  },
  methods : {
    
  }
}
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
