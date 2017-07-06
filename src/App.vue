<template lang="pug">
  #app
    binary-clock
</template>

<script>
  import BinaryClock from './components/BinaryClock'

  export default {
    components: {
      BinaryClock
    }
  }
</script>

<style lang="scss">
  html, body, #app {
    height: 100%;
  }

  #app {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #27292c;
  }
</style>
