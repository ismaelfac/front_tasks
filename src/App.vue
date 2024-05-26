<template>
  <div id="app">
      <task v-bind:Task="tasks"></task>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Task from './components/TasksComponent.vue';

export default defineComponent({
  name: 'App',
  components: {
    Task
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
