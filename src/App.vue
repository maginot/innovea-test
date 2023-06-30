<template>
  <h1>{{ title }}</h1>
  <news-list />
</template>

<script>

  import NewsList from './components/NewsList';

  export default {
    data() {
      return {
        title: 'Innovea Teste'
      }
    },
    components: { NewsList }
  }
</script>

<style scoped>
  h1 {
    font: normal 2em arial;
  }
</style>