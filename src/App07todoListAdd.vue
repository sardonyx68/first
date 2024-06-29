<template>
  <div>

    <img src="./assets/images/main_4.jpg" width="300" height="150">
    <p></p>


    <input type="text" v-model="todoText" size="15" @keyup.enter="insertTodo"/>
    <button @click="insertTodo">todo등록</button>
    
    <div v-for = "( item ) in todoList" :key="item" style="color:coral;" >
      <input type="checkbox">
        {{ ( item.checked ) }} &nbsp; {{ item.id }} - {{ item.text }}
    </div>

    <hr color="blue" size="3" />

    <BoardTest />
  </div>
</template>

<script>
//import Hello from './components/HelloWorld.vue'
//import BoardTest from './components/BoardTest.vue'

export default {
  name: 'App',
  //components: { Hello }
  //components : { BoardTest },
  data() {
    return {
      kind : "Cat",
      todoText : "",
      count : 1,
      todoList : [
                { id : 1, text : "kim", checked : false },
                { id : 2, text : "lee",  checked : true  },
            ]
    }
  },
  methods : {
    insertTodo() {
      //alert( this.todoText + " insertTodo 메소드"+ this.todoList.length );
      
      var max = this.todoList.reduce( function( a, b ) {
          console.log( "a : ",  a , ", b : " , b);
          
          return a > b ? a : b.id;
      })

      this.todoList.push({
        //id : ( this.todoList.length + 1 ),
        id : max + 1,
        text : this.todoText,
        checked : false
      });
      this.todoText = "";
    },
  }
}
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
