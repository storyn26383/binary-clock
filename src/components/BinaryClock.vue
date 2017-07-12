<template lang="pug">
  .binary-clock
    .switch(@click="trueMode = !trueMode")
      light(:on="trueMode")
      | True Binary Mode
    .bcd-mode(v-if="!trueMode")
      binary-coded-decimal-number(:number="hours")
      binary-coded-decimal-number(:number="minutes")
      binary-coded-decimal-number(:number="seconds")
    .true-mode(v-if="trueMode")
      binary-number(:bit="6", :number="0")
      binary-number(:bit="6", :number="hours")
      binary-number(:bit="6", :number="minutes")
      binary-number(:bit="6", :number="seconds")
</template>

<script>
  import Light from './Light'
  import BinaryNumber from './BinaryNumber'
  import BinaryCodedDecimalNumber from './BinaryCodedDecimalNumber'

  export default {
    components: {
      Light, BinaryNumber, BinaryCodedDecimalNumber
    },
    data () {
      return {
        trueMode: false,
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
    .bcd-mode {
      display: flex;
      flex-direction: row;
    }

    .true-mode {
      display: flex;
      flex-direction: column;
    }
  }
</style>
