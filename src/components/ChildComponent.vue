<template>
    <div>
        <slot name="mypage" :age="age" :city="city"></slot>
    </div>
</template>

<script>
export default {
    name : 'ChildComponent',
    data() {
        return {
        age : 1200,
        city : '안국역'
        }
    }
}
</script>

<style>

</style>