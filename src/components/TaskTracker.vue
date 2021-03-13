<template>

<div class="section">
  <div class="nes-container with-title is-centered">
    <p class="title">
      Task Tracker
    </p>

    <button :class="['nes-btn', !toggleForm ? 'is-success': 'is-error']" @click="onToggle">{{ toggleForm ? 'Close' : 'Add a task'}}</button>


    <add-task v-on:add-task="addTask" v-show="toggleForm"/>
    <task-list :tasks="tasks" v-on:delete-task="deleteTask" v-on:mark-completed="markComplete" />
    
    
  </div>

</div>

</template>


<script>
import AddTask from "./AddTask.vue";
import TaskList from './TaskList.vue';

export default {
  components: { AddTask, TaskList },
  name: 'TaskTracker',
  data () {
    return {
      tasks: [
        {id: 1, name: 'Pickup the kids', desc: 'Go to the school to pickup the kids', completed: false},
        {id: 2, name: 'Go to the pub', desc: 'Go to the pub and happy with the friends', completed: true}
      ],
      toggleForm: false
    }
  },
  methods: {
    addTask(task) {
      this.tasks = [...this.tasks, task];

    },
    deleteTask(id) {
      this.tasks = this.tasks.filter(
        (task) => task.id !== id
      )
    },
    markComplete(id) {
      const targetTask = this.tasks.find(
        (task) => task.id === id
      )

      targetTask.completed = !targetTask.completed

      this.task = [...this.task.filter((task) => task.id !== id), targetTask]
    },
    onToggle() {
      this.toggleForm = !this.toggleForm
    }

  },
}
</script>



