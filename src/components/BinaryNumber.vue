<template lang="pug">
  .binary-number
    light(:on="!!(number & (2 ** (bit - i)))", :key="i", v-for="i in bit")
</template>

<script>
  import Light from './Light'

  export default {
    components: {
      Light
    },
    props: {
      bit: {
        type: Number,
        required: true
      },
      number: {
        type: Number,
        required: true
      }
    }
  }
</script>

<style lang="scss" scoped>
  .binary-number {
    display: flex;
    flex-direction: row;
  }
</style>
