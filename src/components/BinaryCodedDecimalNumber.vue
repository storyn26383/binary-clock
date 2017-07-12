<template lang="pug">
  .binary-coded-decimal-number
    binary-number(:bit="4", :number="tens")
    binary-number(:bit="4", :number="ones")
</template>

<script>
  import BinaryNumber from './BinaryNumber'

  export default {
    components: {
      BinaryNumber
    },
    props: {
      number: {
        type: Number,
        required: true
      }
    },
    computed: {
      ones () {
        return this.number % 10
      },
      tens () {
        return Math.floor(this.number / 10)
      }
    }
  }
</script>

<style lang="scss" scoped>
  .binary-coded-decimal-number {
    display: flex;
    flex-direction: row;

    .binary-number {
      display: flex;
      flex-direction: column;
    }
  }
</style>
