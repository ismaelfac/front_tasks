<template>
    <div class="container">
      <div class="task">
        <!-- title -->
        <div class="title">
          <h1> Lista de Tareas</h1>
        </div>
        <!-- form -->
        <div class="form">
          <input
            type="text"
            placeholder="Nueva Tarea"
            v-model="newTask"
            @keyup.enter="addTask"
          />
          <button @click="addTask"><i class="fa fa-plus"></i></button>
        </div>
        <!-- task lists -->
        <div class="taskItems">
          <ul>
            <task-item
              v-bind:task="task"
              v-for="(task, index) in tasks"
              :key="task.id"
              @remove="removeTask(index)"
              @complete="completeTask(task)"
            ></task-item>
          </ul>
        </div>
        <!-- buttons -->
        <div class="clearBtns">
          <button @click="clearCompleted">Clear completed</button>
          <button @click="clearAll">Clear all</button>
        </div>
        <!-- pending task -->
        <div class="pendingTasks">
          <span>Pending Tasks: {{ incomplete }}</span>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import TaskItem from "./TaskDetails.vue";
  
  export default {
    name: "TaskComponent",
    props: ['tasks'],
    components: {
      TaskItem,
    },
    data() {
      return {
        newTask: "",
      };
    },
    computed: {
      incomplete() {
        return []; //this.tasks.filter(this.inProgress).length;
      },
    },
    methods: {
      addTask() {
        console.log('tasks'+ this.tasks);
        if (this.newTask) {
          // this.tasks.push({
          //   title: this.newTask,
          //   completed: false,
          // });
          // this.newTask = "";
        }
      },
      inProgress(task) {
        //return !this.isCompleted(task);
      },
      isCompleted(task) {
        return task.completed;
      },
      clearCompleted() {
        //this.tasks = this.tasks.filter(this.inProgress);
      },
      clearAll() {
       // this.tasks = [];
      },
      completeTask(task) {
        task.completed = !task.completed;
      },
      removeTask(index) {
       // this.tasks.splice(index, 1);
      },
    },
  };
  </script>  