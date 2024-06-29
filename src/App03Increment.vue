<template>
  <h2> App.vue문서</h2>
  <img src="./assets/images/a1.png" width="300" height="150">
  
  <p></p>
  디저트 : {{ kind }}<br>
  안내문 : {{ info }}<br>
  <h3> 카운트 : {{ count }} </h3> <p></p>

  <button @click="suIncrement">증가1</button>
  <button @click="suDecrement">감소1</button> &nbsp;

  <button v-on:click="suIncrement">증가2</button>
  <button v-on:click="suDecrement">감소2</button> &nbsp;

  <hr color="blue" size="3" />
</template>

<script>
//import Hello from './components/HelloWorld.vue'

export default {
  name: 'App',
  //components: { Hello }
  data() {
    return {
      kind : "녹차cake",
      count : 100,
      info : "안내문"
    }
  },
  methods : {
    suIncrement() {
      this.count = this.count + 1;
      this.info  = this.count;
    },
    suDecrement() {
      this.count = this.count - 1;
      this.info  = this.count;
    }
  }
}
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
