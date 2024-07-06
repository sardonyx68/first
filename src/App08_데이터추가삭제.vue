<template>
  <div>

    <img src="./assets/images/a3.png" width="300" height="150">
    <p></p>
   <form @submit.prevent="addGuest"> <!--sap 한페이지처럼 운영 = 뷰, 리액트, angula, svelte-->
      <input type="text" v-model="newTitle" size="15" placeholder="enter title"> <!--placeholder 안내문-->
      <button type="submit">서브밋추가</button>
  </form>
      <div v-for="(item, index) in guests" :key="item.id">
          {{index + 1}} - {{ item.title }}
          <button @click="deleteGuest(item.id)">삭제</button>
      </div>
  </div>
</template>

<script>
import axios from 'axios';


export default {
  name: 'App',
 
  data() {
    return {
      guests: [],
      newTitle : ''
    }
  },
  methods : {
    addGuest(){

      if ( this.newTitle.trim() === '' ) { 
        alert("내용을 입력해주세요");
        return; 
      }
      const newGuest = { title : this.newTitle };

      //입력값 저장
      axios.post("http://localhost:3000/guests", newGuest)
      .then( response => {
        this.guests.push( response.data );
        this.newTitle = '';
      })
      .catch(error => {
        console.log(":::  addGuest Error ::::", error)
      })
      // .finally({});
    },
    //삭제처리
    deleteGuest(id){
      axios.delete(`http://localhost:3000/guests/${id}`)
      .then( () => {
        var index = this.guests.findIndex( pt => { return pt.id === id;} );
        this.guests.splice(index, 1);
      })
      .catch(error => {
        console.log(":::  deleteGuest Error ::::", error)
      })
    },

    displayGuest() {  //db.json문서 데이터 id, title 항목 읽어오기
      axios.get("http://localhost:3000/guests")
      .then( response => {
        this.guests = response.data;
      })
      .catch(error => {
        console.log(":::  displayGuest Error ::::", error)
      })
      // .finally({});

    }

  },
  created() {  //vue라이프사이클에서 mounted(), created() 뷰생성될때 자동인하는 함수
    this.displayGuest();
  }
}
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
