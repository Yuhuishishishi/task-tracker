<template>

<div class="nes-container is-rounded  with-title" @dblclick="$emit('mark-completed')">
    <p :class="['title', task.completed && 'completed']" > 
        {{task.name}}
    </p>
    <p :class="task.completed && 'completed'">
        {{ task.desc}}
        <i class="nes-icon close is-small" style="color: white" @click="$emit('delete-task')"></i>
    </p>
</div>

</template>


<script>
export default {
    name: 'Task',
    props: ['task']
}
</script>


<style scoped>
.completed {
    text-decoration: line-through;
}

div {
    margin: 2rem !important
}


</style>