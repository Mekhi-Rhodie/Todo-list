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

  <main>
    <TodoList />
  </main>
</template>

<style scoped>

</style>
