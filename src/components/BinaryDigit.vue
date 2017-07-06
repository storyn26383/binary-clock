<template lang="pug">
  .binary-digit
    .digit
      light(:on="!!(tens & 8)")
      light(:on="!!(tens & 4)")
      light(:on="!!(tens & 2)")
      light(:on="!!(tens & 1)")
    .digit
      light(:on="!!(ones & 8)")
      light(:on="!!(ones & 4)")
      light(:on="!!(ones & 2)")
      light(:on="!!(ones & 1)")
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
