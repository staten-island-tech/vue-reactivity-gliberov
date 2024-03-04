<template>
    <h1>Welcome To Gabe's Piano App</h1>
    <h2>The CSS is soooo good right?</h2>
    <h3>Warning: If you are not a musician I advise you not to press play chord with a bunch of notes at once. Please don't sue me if you need hearing aids.</h3>
    <div class="home-view">
      <Piano @reset="reset" />
    </div>
  </template>
  
  <script>
  import Piano from '../components/Piano.vue';
  
  export default {
    components: {
      Piano
    },
    methods: {
      reset() {
      }
    }
  }
  </script>
  
  <style scoped>
  .home-view {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }

  .piano-key {
    display: inline-block;
  }
  </style>