<template>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"/>

  <nav id="topMenu" class="navbar navbar-expand navbar-light bg-white topbar mb-4 static-top shadow d-flex">
    <div class="flex-fill">
      <h3>Slashrand Application</h3>
    </div>
  </nav>

  <div id="app" class="position-absolute top-50 start-50 translate-middle">
    <div class="my-3">
      <transition enter-active-class="animate__animated animate__bounceIn" leave-active-class="animate__animated animate__fadeOut animate__fast">
        <h1 style="position: absolute; top: -40px; left: 0; right: 0;" v-if="anime">{{ nextRand }}</h1>
      </transition>
      <transition enter-active-class="animate__animated animate__bounceIn" leave-active-class="animate__animated animate__fadeOut animate__fast">
        <h1 style="position: absolute; top: -40px; left: 0; right: 0;" v-if="!anime">{{ currentRand }}</h1>
      </transition>
    </div>

    <button type="button" class="btn btn-outline-secondary" @click="randomize">Randomize</button>
  </div>
</template>

<script>

export default {
  data() {
    return {
      anime: false,
      nextRand: null,
      currentRand: null,
      max: 100
    }
  },
  methods: {
    randomize() {
      this.currentRand = Math.floor(Math.random() * this.max) + 1;
      this.nextRand = Math.floor(Math.random() * this.max) + 1;

      this.anime = !this.anime
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
</style>
