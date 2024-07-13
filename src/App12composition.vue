<template>
  <div>
    <h3>컴포지션api json-server 접근 테스트 10:17</h3>
    <img src="./assets/images/main_4.jpg" width="300" height="150">
    <p></p>
   <form @submit.prevent="addGuest"> <!--sap 한페이지처럼 운영 = 뷰, 리액트, angula, svelte-->
      <input type="text" v-model="newGuest.title" size="15" placeholder="enter title"> <!--placeholder 안내문-->
      <button type="submit">서브밋추가</button>
      <p vi-if="errorMessage" sylte="color:red;">{{ errorMessage }}</p>
  </form>
      <div v-for="(item, index) in guests" :key="item.id">
          {{index + 1}} - {{ item.title }}
          <button @click="deleteGuest(item.id)">삭제</button>
      </div>
  </div>
</template>


<script setup>
import axios from 'axios';
import {ref, onMounted} from 'vue';

const guests = ref([]);
const newGuest = ref({ title: '' });
const errorMessage = ref('');

//json-server --watch db.json실행할때 command prompt에서 실행
//컴포지션api는 화살표함수 접근 const 이름 = (data) => 구현
//컴포지션api는 최대한 this사용금지
const displayGuest = () =>   //db.json문서 데이터 id, title 항목 읽어오기
    axios.get("http://localhost:3000/guests")
    .then( response => {
      guests.value = response.data;
    })
    .catch(error => {
      console.log(":::  composition출력 Error ::::", error)
    })
    // .finally({});

const addGuest = () => {
    if ( newGuest.value.title == '' ) {
      errorMessage.value = "데이터를 입력해주세요";
      return;
    } else if ( newGuest.value.title.length <= 1 ) {
      errorMessage.value = "입력데이터는 최소 2글자부터 입력해주세요";
      newGuest.value = {title:''};
      return;
    } 

    //입력값 저장
    axios.post("http://localhost:3000/guests", newGuest.value)
    .then( response => {
      errorMessage.value = "";
      guests.value.push( response.data );
      newGuest.value = { title:'' }
    })
    .catch(error => {
      console.log(":::  composition저장 Error ::::", error)
    })
    // .finally({});
  }
//삭제처리
const deleteGuest = (id) => 
    axios.delete(`http://localhost:3000/guests/${id}`)
    .then( () => {
      var index = guests.value.findIndex( pt => { return pt.id === id;} );
      guests.value.splice(index, 1);
    })
    .catch(error => {
      console.log(":::  composition삭제 Error ::::", error)
    })

    onMounted( displayGuest );  //Vue라이프사이클 onCreated후 화면보여지는 상태가 onMounted

    //기존자바스크립트에서 함수
    //
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
