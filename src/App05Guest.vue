<template>
  <div>

    <img src="./assets/images/main_4.jpg" width="300" height="150">
    <p></p>

    디저트 : {{ kind }}<br>
    카운트 : {{ count }} <p></p>
    <hr color="blue" size="3" />

    <BoardTest />
  </div>
</template>

<script>
//import Hello from './components/HelloWorld.vue'
import BoardTest from './components/BoardTest.vue'

export default {
  name: 'App',
  //components: { Hello }
  components : { BoardTest },
  data() {
    return {
      kind : "cake",
      count : 500,
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
