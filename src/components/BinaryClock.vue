<template lang="pug">
  .binary-clock
    binary-digit(:number="hours")
    binary-digit(:number="minutes")
    binary-digit(:number="seconds")
</template>

<script>
  import BinaryDigit from './BinaryDigit'

  export default {
    components: {
      BinaryDigit
    },
    data () {
      return {
        hours: 0,
        minutes: 0,
        seconds: 0
      }
    },
    mounted () {
      window.setInterval(() => {
        let now = new Date()

        this.hours = now.getHours()
        this.minutes = now.getMinutes()
        this.seconds = now.getSeconds()
      }, 1000)
    }
  }
</script>

<style lang="scss" scoped>
  .binary-clock {
    display: flex;
    flex-direction: row;

    .binary-digit {
      margin: 0 8px;
    }
  }
</style>
