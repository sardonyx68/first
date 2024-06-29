<template lang="">
    <div>
        <img src="../assets/images/a1.png" width="300" height="150">
        Test.vue 저자 : {{ name }}
        <!-- guest 배열객체 출력  -->
        <div v-for = "(item, index) in guest" :key = "index" >
        번호 : {{ index }}, 이름 : {{ item.name }}, 나이 : {{ item.age }}, 제목 : {{  item.title }} <hr>
        </div>
    </div>
</template>

<script>
export default {
    name : "BoardTest",
    data() {
        return{
            name : "Hong gil dong",
            guest : [
                { name : "kim", age : 23, title : "sunday" },
                { name : "lee", age : 31, title : "monday" },
                { name : "goo", age : 27, title : "friday" }
            ]
        }
    }
}
</script>

<style lang="">
    
</style>