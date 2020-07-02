<template>
    <div class="form">
        <my-input @inputTask="keyUp"/>
        <my-button @click.native="addTodo"/>
    </div>
</template>

<script>
    import Button from "../atoms/Button.vue";
    import Input from "../atoms/Input.vue";

    const componentsList = {};
    componentsList[Button.name] = Button;
    componentsList[Input.name] = Input;

    export default {
        name: "FormTask",
        components: componentsList,
        data(){
            return {
                newTodo: ''
            }
        },
        methods: {
            addTodo(){
                this.$emit('valueInput', this.newTodo);
                this.$children[0].$el.value = '';
            },

            keyUp(newTodo){
                this.newTodo = newTodo === '' ? this.newTodo : newTodo;
            }
        }
    }
</script>