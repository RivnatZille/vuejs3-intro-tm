<template>
  <!-- Content -->
  <div class="px-3 py-10 md:px-10">
    <div class="w-full sm:w-1/2 lg:w-1/3 mx-auto">
      <TodoSpinner v-if="loading" />

      <template v-else>
        <TodoFormAdd />

        <TodoItems v-if="$store.state.todos.length"/>

        <TodoEmpty v-else/>
      </template>
    </div>
  </div>
  <!--/ Content -->
</template>

<script setup>
import TodoSpinner from "./components/TodoSpinner.vue";
import TodoFormAdd from "./components/TodoFormAdd.vue";
import TodoItems from "./components/TodoItems.vue";
import TodoEmpty from "./components/TodoEmpty.vue";
import { ref } from 'vue';
import { useStore } from 'vuex';

// VARIÁVEIS
const loading = ref(false);
const store = useStore();

loading.value = true;

store.dispatch('getTodos')
    .finally(() => {
      loading.value = false;
    });
</script>

<style scoped>

</style>
