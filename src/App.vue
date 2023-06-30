<template>
  <h1>{{ title }}</h1>
  <news-list />
</template>

<script>

  import NewsList from './components/NewsList';

  export default {
    data() {
      return {
        title: 'Innovea Test'
      }
    },
    components: { NewsList }
  }
</script>

<style scoped>

  body {
    background:#c4c4c8;
  }

  h1 {
    font: bold 32px arial;
  }
</style>