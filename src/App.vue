<script setup>
  import Header from './components/Header.vue'
  import TodoList from './components/TodoList.vue'

  components: {
    'Header',
    'TodoList'
  }
</script>

<template>
  <header>
    <Header />
  </header>

  <main class="container-sm">
    <TodoList />
  </main>
</template>

<style scoped>

</style>
