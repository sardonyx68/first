<template>
  <img src="./assets/images/main_4.jpg" width="300" height="150">
  <h3>App.vue 11:07</h3>
  <hr color="blue">
  <ChildComponent>
    <template #mypage="{age, city}">
    나이 : {{ age }} <br>
    도시 : {{ city }}
    </template>
  </ChildComponent>
</template>

<script>
import ChildComponent from './components/ChildComponent.vue'

export default {
  name: 'App',
  components: {
    ChildComponent
  }
}
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
