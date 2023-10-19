<template>
    <div>{{ loudJoke }}</div>
  </template>
  
  <script>
  export default {
    props: ['joke'],
    computed: {
      loudJoke() {
        return this.joke.toUpperCase();
      }
    }
  }
  </script>
  