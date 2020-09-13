<template>
  <div class="linePattern" :style="'background-image: url(' + pattern + ');'"></div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    name: 'LinePattern',
    props: {
      pattern: {
        type: String,
        required: true
      }
    }
  })
</script>

<style scoped lang="scss">
  .linePattern {
    width: 100%;
    height: 12px;
    background-size: auto 100%;
    background-repeat: space;
    @media (max-width: $large) {
      height: 8px;
    }
  }
</style>
