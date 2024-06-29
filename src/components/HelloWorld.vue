<template>
  <div class="hello">
    <h2>{{ kakao }}</h2>
    
    HelloWorld.vue Installed CLI Plugins<br>
    
    HelloWorld.vue Essential Links<br>
    
    HelloWorld.vue Ecosystem<br>
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    kakao: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
