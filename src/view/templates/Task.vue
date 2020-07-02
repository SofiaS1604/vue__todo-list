<template>
    <div class="task">
        <div class="task__text">
           {{text}}
        </div>
        <div class="task__buttons">
            <div v-bind:class="{task__completed__active: completedTask}" @click="$emit('clickButton', ['completed', id])" class="task__completed">&#10004;</div>
            <div @click="$emit('clickButton', ['remove', id])" class="task__remove">&#10008;</div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "MyTask",
        props: ["text", "id", "completedTask"],
    }
</script>
