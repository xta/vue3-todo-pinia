<template>
    <div>
        <h1>To Do List</h1>
        <TodoForm />
        <TodoList />
    </div>
</template>

<script>
import { defineComponent } from "vue";

import TodoForm from './TodoForm.vue'
import TodoList from './TodoList.vue'

export default defineComponent({
  components: { TodoForm, TodoList },
  setup() {
    return {};
  },
});
</script>

<style lang="scss" scoped>

</style>