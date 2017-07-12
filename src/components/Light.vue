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
