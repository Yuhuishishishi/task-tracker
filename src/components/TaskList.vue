<template>
    <div class="nes-container is-rounded list-box">

        <task 
            v-for="task in tasks" 
            :key="task.id" :task="task" 
            v-on:delete-task="$emit('delete-task', task.id)" 
            v-on:mark-completed="$emit('mark-completed', task.id)"
            />
    </div>
</template>


<script>
import Task from './Task.vue'


export default {
    name: 'TaskList',
    props: ['tasks'],
    components: {
        Task
    }
}
</script>

<style scoped>
div {
    margin: 2rem auto auto auto  !important;
}
</style>