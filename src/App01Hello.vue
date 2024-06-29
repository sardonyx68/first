<template>
  <img src="./assets/images/a1.png" width="300" height="150">
  <HelloWorld msg="칠동 Welcome to"/>

  <h2>쉬는시간</h2>
  <hr color="blue" size="3">
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
