<template>
  <div id="app">
    <TaskTracker/>
  </div>
</template>

<script>
import TaskTracker from './components/TaskTracker.vue'

export default {
  name: 'App',
  components: {
    TaskTracker
  }
}
</script>

<style lang="sass">

@import "../node_modules/nes.css/css/nes.css";
// @import "../node_modules/bulma/sass/layout/section.sass";
// @import "../node_modules/bulma/sass/grid/columns.sass";

</style>
