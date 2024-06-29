<template>
  <h2> App.vue문서</h2>
  <img src="./assets/images/main_3.jpg" width="300" height="150">
  <Hello msg="칠동 Welcome to"/>

  <h2>쉬는시간</h2>
  <hr color="blue" size="3">
</template>

<script>
import Hello from './components/HelloWorld'

export default {
  name: 'App',
  components: {
    Hello
  }
}
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
