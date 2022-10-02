<template>
  <div class="space-y-2">
    <TodoItem v-for="todo in $store.state.todos" :key="todo.id" :todo="todo" />
  </div>

  <div v-if="pendingTodosCount > 0" class="m-2 text-white">
    Pendentes: <span class="underline">{{ pendingTodosCount }}</span>
  </div>
</template>

<script setup>
import TodoItem from "./TodoItem.vue";
import { computed } from "vue";
import { useStore } from "vuex";

const store = useStore();

const pendingTodosCount = computed(() => {
  return store.getters.pendingTodos.length;
});
</script>

<style scoped></style>
