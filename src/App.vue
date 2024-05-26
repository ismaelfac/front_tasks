<template>
  <div id="app">
      <nav-bar></nav-bar>
      <task v-bind:tasks="tasks"></task>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Task from './components/TasksComponent.vue';
import NavBar from './components/NavBar.vue';

export default defineComponent({
  name: 'App',
  components: {
    Task,
    NavBar
  },
  data() {
    return {
      tasks: [
        {
          id: 1,
          title: "Learn Vue JS",
          completed: true,
        },
        {
          id: 2,
          title: "Watch netflix",
          completed: true,
        },
        {
          id: 3,
          title: "Go shopping",
          completed: false,
        },
        {
          id: 4,
          title: "Learn guitar",
          completed: false,
        },
        {
          id: 5,
          title: "Send email",
          completed: false,
        },
      ],
    };
  },
});
</script>
