<template lang="pug">
  .light(:class="{ on }")
</template>

<script>
  export default {
    props: {
      on: {
        type: Boolean,
        required: true
      }
    }
  }
</script>

<style lang="scss" scoped>
  $size: 70px;
  $margin: 8px;

  .light {
    display: inline-block;
    width: $size;
    height: $size;
    margin: $margin;
    background-color: darken(#27292c, 1%);

    &.on {
      background-color: #93b2ca;
    }
  }
</style>
