<template lang="">
    <div>
        <button @click="deleteTodo">todo삭제</button>
    </div>
</template>

<script>
export default {
    name : "TodoList",
    data()  {
        return {
            lotto : 1,
        }
    },
    methods : {
        deleteTodo() {
            console.log( 'TodoList deleteTodo 함수' );
        },
        toggleCheckbox() {
            console.log( 'TodoList.toggleCheckbox 함수' );
        }
    },
}
</script>

<style lang="">
    
</style>
