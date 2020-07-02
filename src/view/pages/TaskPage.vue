<template>
    <div class="page">
        <form-task @valueInput="newTask"/>
        <task-list :tasks="this.tasks"/>
    </div>
</template>

<script>
    import FormTask from '../templates/FormTask.vue';
    import TaskList from '../widgets/TaskList.vue';

    const componentsList = {};
    componentsList[FormTask.name] = FormTask;
    componentsList[TaskList.name] = TaskList;

    export default {
        name: "TaskPage",
        components: componentsList,
        props: ["user"],
        data(){
            return{
                tasks: [],
            }
        },
        methods: {
            newTask(newTodo){
                this.tasks.push({id: this.tasks.length, text: newTodo, completedTask: false});
            }
        }
    }
</script>
