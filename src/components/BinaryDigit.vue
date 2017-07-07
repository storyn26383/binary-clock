<template lang="pug">
  .binary-digit
    .digit(:key="index", v-for="(digit, index) in [tens, ones]")
      light(:on="!!(digit & (2 ** (4 - i)))", :key="i", v-for="i in 4")
</template>

<script>
  import Light from './Light'

  export default {
    components: {
      Light
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
  .binary-digit {
    display: flex;
    flex-direction: row;

    .digit {
      display: flex;
      flex-direction: column;
    }
  }
</style>
