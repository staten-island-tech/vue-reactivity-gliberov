<template>
    <div class="chord">
      <p v-if="Chord.length === 0">No notes played</p>
      <p v-else>Sequence {{ Chord.length }}: {{ Chord.join(', ') }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      Chord: Array
    }
  };
  </script>
  
  <style scoped>

  </style>