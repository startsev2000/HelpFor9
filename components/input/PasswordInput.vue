<template>
  <div class="passwordInput">
    <img class="logo" src="/img/logos/lock.svg">
    <input :type="hidden ? 'password' : 'text'">
    <img @click="toggleInputView" class="toggleButton" src="/img/logos/eye.svg" />
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    name: 'PasswordInput',
    data() {
      return {
        hidden: true
      }
    },
    methods: {
      toggleInputView() {
        this.hidden = !this.hidden
      }
    }
  })
</script>

<style scoped lang="scss">
  .passwordInput {
    display: flex;
    background-color: white;
    padding: 16px 24px;
    border-radius: 32px;
    box-shadow: 1px 2px 2px rgba(0, 0, 0, 0.05), -1px 0px 2px rgba(0, 0, 0, 0.05);
    input {
      border: 0;
      outline: 0;
      font-size: 16px;
      font-family: 'Montserrat';
      letter-spacing: 0.02em;
      font-weight: 500;
      width: 100%;
    }
    img {
      display: inline;
      height: 24px;
    }
    .logo {
      margin: auto 12px auto 0;
    }
    .toggleButton {
      cursor: pointer;
      margin: auto 0 auto 12px;
    }
  }
</style>
