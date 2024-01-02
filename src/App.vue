<template>
  <header>
    <h1>slashrand application</h1>
  </header>
  <label>Current rand : {{ randNumber }}</label>
  <button @click="randomize">Randomize</button>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      randNumber: null,
      max: 100
    }
  },
  methods: {
    randomize() {
      this.randNumber = Math.floor(Math.random() * this.max) + 1;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

header {
  top: 0;
  width: 100%;
  background-color: aquamarine;
}
</style>
