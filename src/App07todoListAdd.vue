<template>
  <div>

    <img src="./assets/images/main_4.jpg" width="300" height="150">
    <p></p>

    <!-- 첫번째 방법 (권장)
    <input type="text" v-model="todoText" size="15" @keyup.enter="insertTodo"/> 
    -->
    <input type="text" ref="todoText" size="15" @keyup.enter="insertTodo"/>
    
    <button @click="insertTodo">todo등록</button>

    <div v-for = "( item ) in todoList" :key="item" style="color:coral;" >
        {{ ( item.checked ) }} &nbsp; {{ item.id }} - {{ item.text }}
    </div>

    <hr color="blue" size="3" />

    <Hello kakao="모란백합 Hello"/>

    <!-- @click-delete : [-이름] 표시함 -->
    <!--:skytodo 실제 데이터-->
    <TodoTest v-for= "(item) in todoList" :key="item.id" :skytodo="item" 
        @click-delete="deleteTodo" v-on:toggle-checkbox="greenCheckbox">

    </TodoTest>
    <!-- <BoardTest /> -->
  </div>
</template>

<script>
//import Hello from './components/HelloWorld.vue'
import TodoTest from './components/TodoTest.vue'
//import BoardTest from './components/BoardTest.vue'

export default {
  name: 'App',
  components: { TodoTest },
  //components: { Hello, TodoTest },
  //components : { BoardTest },
  //components : { TodoTest },
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
          
          return a > b.id ? a : b.id;
      })

      this.todoList.push({
        //id : ( this.todoList.length + 1 ),
        id : max + 1,
        // text : this.todoText,
        text: this.$refs.todoText.value,
        checked : false
      });
      // this.todoText = "";
      this.$refs.todoText.value = '';
      localStorage.setItem( "young", JSON.stringify(this.todoList) );
    }, //등록

    //웹브라우저 storge연결
    deleteTodo( id ) {
      var max = this.todoList.reduce( function( a, b ) {
          console.log( "a : ",  a , ", b : " , b);
          
          return a > b.id ? a : b.id;
      })
      
      //배열추가 push, 대표값추출 reduce(),  찾아서 findIndex()
      //todoList 배열 데이터 추가는 App.vue처리하고, 삭제는 새로 만든 컴포넌트 TodoList.vue처리
      id = max;
      var index = this.todoList.findIndex( mytodo =>{ return mytodo.id === id });   //7월6일 삭제처리 여기서부터 시작
      this.todoList.splice(index, 1); //삭제
      localStorage.removeItem(index); //스토리지 내용삭제

      console.log( id )
    },  //삭제

    greenCheckbox( {id, checked }) {  //push, findindex, reduce
      console.log( 'greenCheckbox 함수')
      var index = this.todoList.findIndex( mytodo =>{ return mytodo.id === id });
      this.todoList[index].checked = checked;

    }, //체크박스

  }
}
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
