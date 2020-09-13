<template>
  <div class="buttonSecondary">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'ButtonSecondary'
  }
</script>

<style scoped lang="scss">
  .buttonSecondary {
    cursor: pointer;
    display: inline-block;
    color: black;
    font-size: 13px;
    font-weight: 700;
    font-family: 'Ubuntu';
    text-transform: uppercase;
    letter-spacing: 0.04em;
    background-color: $secondary-color-light;
    padding: 8px 16px;
    border: solid 5px $primary-color-light;
    box-shadow: 4px 4px 8px rgba(0, 0, 0, 0.08);
    border-radius: 12px 12px 0 0;
    transition: 300ms ease-out;
    &:hover, &:focus {
      box-shadow: 4px 4px 8px rgba(0, 0, 0, 0.2);
    }
  }
</style>
