<template lang="pug">
  .true-binary-digit
    light(:on="!!(number & 32)")
    light(:on="!!(number & 16)")
    light(:on="!!(number & 8)")
    light(:on="!!(number & 4)")
    light(:on="!!(number & 2)")
    light(:on="!!(number & 1)")
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
