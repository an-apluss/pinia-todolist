<script setup>
import { ref } from "vue";
import { useTodoStore } from "../stores/Todo"

const todo = ref(null);
const todoStore = useTodoStore();

const handleAddTodoList = (item) => {
    if (item?.length === 0) {
        return
    }

    todoStore.addTodoList(item);
    todo.value = null;
}

</script>
<template>
    <div>
        <form @submit.prevent="handleAddTodoList(todo)">
            <input type="text" v-model="todo">
            <button >Add</button>
        </form>
    </div>
</template>
<style scoped>
  form {
    margin-bottom: 15px;
  }
  input {
    margin-top: 25px;
    margin-bottom: 15px;
    height: 20px;
    width: 50%;
  }
  button {
    margin-left: 30px;
    background-color: #2f6089;
    padding: 5px 10px;
    border: none;
    border-radius: 5px;
    font-weight: 800;
    color: white;
    width: 15%;
  }
  .alert-div {
    min-height: 25px;
  }
  .alert {
    color: #d1495b;
    font-size: 1em;
    font-weight: 600;
  }
</style>