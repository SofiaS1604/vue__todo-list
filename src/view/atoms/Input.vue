<template>
    <input type="text" class="form__input" @keyup="keyUp" v-model="newTodo" placeholder="Inter text task"/>
</template>

<script>
    export default {
        name: "MyInput",
        data() {
            return{
                newTodo: '',
            }
        },
        methods: {
            keyUp() {
                this.$emit('inputTask', this.newTodo)
            }
        }
    }
</script>