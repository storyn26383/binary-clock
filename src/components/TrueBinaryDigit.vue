<template lang="pug">
  .true-binary-digit
    light(:on="!!(number & (2 ** (6 - i)))", :key="i", v-for="i in 6")
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
    }
  }
</script>

<style lang="scss" scoped>
  .binary-digit {
    display: flex;
    flex-direction: row;
  }
</style>
