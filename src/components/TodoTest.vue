<template lang="">
    <div>
        <!--:skytodo="item"  @click-delete="deleteTodo" v-on:toggle-checkbox="greenCheckbox"-->
        <input type="checkbox" :checked="skytodo.checked" @change="myToggleCheckbox"> {{skytodo.checked}}

        <span :style="skytodo.checked ? 'text-decoration:line-through' : '' ">
            {{skytodo.id}} - {{skytodo.text}}
        </span>
        <button @click="myDeleteTodo">삭제</button>
    </div>
</template>

<script>
export default {
    name : "TodoList",
    props : {       //값을 전달 받음
        skytodo : { type: Object, required: true }
    },
    // data()  {
    //     return {
    //         skytodo : { type: Object, required: true }
    //     }
    // },
    methods : {
        myDeleteTodo() {
            console.log( 'TodoTest MyDeleteTodo 함수' );
            this.$emit( 'click-delete', this.skytodo.id );       //app.vue에서 값을 받는
        },
        myToggleCheckbox(event) {
            console.log( 'TodoTest.MyToggleCheckbox 함수' );

             //app.vue에서 값을 받는, {}는 인자를 한개이상 받아오기위해서 사용
            this.$emit( 'toggle-checkbox', {
                id: this.skytodo.id,
                checked: event.target.checked
            })
        }
    },
}
</script>

<style lang="">
    
</style>
