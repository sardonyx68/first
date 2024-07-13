<template>
    <img src="@/assets/images/main_4.jpg" width="300" height="150">
    <p></p>
    <h2> App.vue 문서</h2>
    <form @submit.prevent="addGuest">
        제목 : <input type="text" name="title" placeholder="제목입력">
        제목 : <input type="text" name="age" placeholder="나이입력">
        제목 : <input type="file">
    </form>
  
    <button @submit=""></button>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
}
</script>
