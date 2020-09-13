<template>
  <div class="textInput">
    <img :src="logo">
    <input type="text">
  </div>
</template>

<script lang="ts">
  export default {
    name: 'TextInput',
    props: {
      logo: {
        type: String,
        required: true
      }
    }
  }
</script>

<style scoped lang="scss">
.textInput {
  display: flex;
  background-color: white;
  padding: 16px 24px;
  border-radius: 32px;
  box-shadow: 1px 2px 2px rgba(0, 0, 0, 0.05), -1px 0px 2px rgba(0, 0, 0, 0.05);
  img {
    display: inline;
    height: 24px;
    margin: auto 12px auto 0;
  }
  input {
    border: 0;
    outline: 0;
    width: 100%;
    font-size: 16px;
    font-family: 'Montserrat';
    letter-spacing: 0.02em;
    font-weight: 500;
  }
}
</style>
