<template>
  <img src="./assets/images/main_2.jpg" width="300" height="150">
  
  <h2>App.vue 문서 2:15</h2>
  <!-- <hr color="blue" size="3"> -->
  
  App.vue 이름 {{  name }} 입니다. <br>
  App.vue 역량 {{  hp }} 입니다. <br>

  <SonComponent v-model:name="name" v-model:hp="hp" ></SonComponent>
</template>

<script>
import SonComponent from './components/SonComponent'

export default {
  name: 'App',
  components: {
    SonComponent
  },
  data(){
    return{
      name :'bmedic',
      hp: 780
    }
  }
}
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
