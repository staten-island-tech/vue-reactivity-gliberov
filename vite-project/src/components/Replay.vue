<template>
    <div>
      <button @click="replayMelodic" class="replay">Play Melodic!</button>
      <button @click="replayChord" class="replay">Play Chord!</button>
      <button @click="reset" class="reset">Reset Sequence!</button>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      replayChord() {
        this.$emit("replay-chord");
      },
  
      replayMelodic() {
        this.$emit("replay-melodic");
      },
  
      reset() {
        this.$emit("reset-sequence");
      }
    }
  };
  </script>
  
  <style scoped>
.replay {
  background-color: #4CAF50; 
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  transition-duration: 0.4s;
}

.reset {
  background-color: #f44336; 
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  transition-duration: 0.4s;
}
  </style>