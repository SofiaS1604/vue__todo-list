<template>
       <div class="task__list" :key="renderTasks">
           <div v-for="task in this.tasks">
               <my-task :completedTask="task.completedTask"  :id="task.id" :text="task.text" @clickButton="clickButton"/>
           </div>
       </div>
</template>

<script>
    import MyTask from '../templates/Task.vue';

    const componentsList = {};
    componentsList[MyTask.name] = MyTask;

    export default {
        name: "TaskList",
        components: componentsList,
        props: ['tasks'],
        data(){
            return{
                renderTasks: 0,
            }
        },
        methods: {
            clickButton(taskInfo){
                let task = this.tasks.filter(task => task.id === +taskInfo[1]);
                if(taskInfo[0] === 'completed'){
                    task[0].completedTask = !task[0].completedTask;
                }else{
                    let indexTask = this.tasks.findIndex(task => task.id === +taskInfo[1]);
                    this.tasks.splice(indexTask, 1)
                }

                this.renderTasks ++;
            }
        }
    }
</script>

<style scoped>

</style>