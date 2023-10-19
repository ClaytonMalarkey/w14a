<template>
    <div>{{ snakeJoke }}</div>
  </template>
  
  <script>
  export default {
    props: ['joke'],
    computed: {
      snakeJoke() {
        return this.joke.replace(/ /g, '_');
      }
    }
  }
  </script>
  