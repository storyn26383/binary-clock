<template lang="pug">
  .binary-clock
    .switch(@click="trueMode = !trueMode")
      light(:on="trueMode")
      | True Binary Mode
    .bcd-mode(v-if="!trueMode")
      binary-digit(:number="hours")
      binary-digit(:number="minutes")
      binary-digit(:number="seconds")
    .true-mode(v-if="trueMode")
      true-binary-digit(:number="hours")
      true-binary-digit(:number="minutes")
      true-binary-digit(:number="seconds")
</template>

<script>
  import Light from './Light'
  import BinaryDigit from './BinaryDigit'
  import TrueBinaryDigit from './TrueBinaryDigit'

  export default {
    components: {
      Light, BinaryDigit, TrueBinaryDigit
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
    .switch {
      margin-left: 8px;
      font-family: monospace;
      color: #9ac9c4;
      font-size: 20px;
      display: flex;
      align-items: center;
      cursor: pointer;

      .light {
        width: 35px;
        height: 35px;
        margin-right: 16px;

        &.on {
          background-color: #9ac9c4;
        }
      }
    }

    .bcd-mode {
      display: flex;
      flex-direction: row;

      .binary-digit {
        margin: 0 8px;
      }
    }

    .true-mode {
      display: flex;
      flex-direction: column;

      .true-binary-digit {
        margin: 8px;
      }
    }
  }
</style>
