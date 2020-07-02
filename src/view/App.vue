<template>
   <task-page/>
</template>

<script>
    import TaskPage from './pages/TaskPage.vue';

    const componentsList = {};
    componentsList[TaskPage.name] = TaskPage;

    export default {
        name: 'App',
        components: componentsList,
    };
</script>
