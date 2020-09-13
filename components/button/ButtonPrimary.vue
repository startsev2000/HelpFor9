<template>
  <div class="buttonPrimary">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'ButtonPrimary'
  }
</script>

<style scoped lang="scss">
  .buttonPrimary {
    color: white;
    padding: 12px 32px;
    text-align: center;
    font-size: 20px;
    font-weight: bold;
    font-family: 'Montserrat';
    background-color: $primary-color;
    border-radius: 8px;
    box-shadow: 2px 2px 2px rgba(0, 0, 0, 0.07), -2px -2px 7px rgba(0, 0, 0, 0.05);
  }
</style>
