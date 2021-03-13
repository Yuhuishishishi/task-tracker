<template>
    <div class="nes-container with-title">
        <p class="title">
            Add a Task
        </p>

        <form>
            <div class="nes-field">
                <label for="task_name">Task name</label>
                <input type="text" class="nes-input" id="task_name" v-model="name">
            </div>

            <br>

            <div class="nes-field">
                <label for="task_desc">Task description</label>
                <textarea id="task_desc" class="nes-textarea" v-model="desc"></textarea>
            </div>

            <br>

            <input type="submit" value="Add a task" class="nes-btn" @click.prevent="onSubmit">

        </form>


    </div>


</template>

<script>
export default {
    name: 'AddTask',
    data() {
        return {
            name: '',
            desc: ''
        }
    },
    methods: {
        onSubmit() {
            const newTask = {
                id: Math.round(Math.random() * 10000),
                name: this.name,
                desc: this.desc,
                completed: false
            }

            this.$emit('add-task', newTask);

            this.name = '';
            this.desc = '';

        }
    }
}
</script>

<style scoped>
div .nes-container {
    margin-top: 2rem !important;
}


</style>