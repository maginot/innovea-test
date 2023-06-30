<template>
  <div align="center" class="border-bottom">
    <img src="logo.png" height="60" :alt="title"/>
  </div>
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

<style>
  body {
    background:#090d30 !important;
  }

  h1 {
    font: bold 32px arial;
    color: white;
  }

  .border-bottom {
    border-bottom: 2px solid white;
  }

</style>