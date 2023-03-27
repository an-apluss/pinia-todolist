<script setup>
import TodoForm from "./TodoForm.vue";
import TodoList from "./TodoList.vue";

</script>
<template>
    <div class="todo-app">
        <h2>To Do List</h2>
        <todo-form></todo-form>
        <todo-list></todo-list>
    </div>
</template>
<style scoped>
  .todo-app {
    padding: 5vh;
    min-height: 100vh;
    width: 30vw;
    background-color: #f7f9fc;
    margin: 0 auto;
  }
</style>