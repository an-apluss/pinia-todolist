<script setup>
    import { storeToRefs } from "pinia";
    import { useTodoStore } from "../stores/Todo"
    
    const todoStore = useTodoStore();
    const { todoList } = storeToRefs(todoStore);
    const { toggleCompleted, deleteTodoList } = todoStore;

</script>
<template>
    <div v-for="todo in todoList" :key="todo.id" class="item">
        <div class="content">
            <span :class="{ completed: todo.completed }">
                {{ todo.item }}
            </span>
            <div>
                <span class="pointer" @click.stop="toggleCompleted(todo.id)">&#10004;</span>
                <span class="pointer x" @click="deleteTodoList(todo.id)">&#10060;</span>
            </div>
        </div>
    </div>
</template>
<style scoped>
  span {
    margin: 0 10px;
    cursor: pointer;
  }
  .item {
    display: flex;
    justify-content: center;
  }
  .content {
    display: flex;
    font-size: 1.5em;
    justify-content: space-between;
    width: 80vw;
    padding: 5px;
  }
  .completed {
    text-decoration: line-through;
  }
</style>