<template>
    <div v-for="todo in todoList" :key="todo.id">
    <div>
      <span @click.stop="toggleCompleted(todo.id)">&#10004;</span>
      <span :class="{ completed: todo.completed }">{{ todo.item }}</span>
      <span @click="deleteTodo(todo.id)">&#10060;</span>
    </div>
  </div>
</template>

<script>
import { useTodoListStore } from "../store/useTodoListStore";
import { storeToRefs } from "pinia";

export default {
  setup() {
    const store = useTodoListStore();
    // storeToRefs lets todoList keep reactivity:
    const { todoList } = storeToRefs(store);

    // destructuring action method doesn't require using storeToRefs:
    const { toggleCompleted, deleteTodo } = store;

    return { todoList, toggleCompleted, deleteTodo };
  },
};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
}
</style>