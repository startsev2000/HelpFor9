<template>
  <div class="directionCard" @click="goTo">
    <div v-if="type === 0">
      <img :src="image" style="width: 100%;">
      <span>{{ text }}</span>
    </div>
    <div v-else-if="type === 1">
      <img :src="image" style="width: 80%; margin: 24px auto 0;">
      <span>{{ text }}</span>
    </div>
    <div v-else>
      <img :src="image" style="width: 100%; margin: 54px 0 0;">
      <span>{{ text }}</span>
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    name: 'DirectionCard',
    props: {
      type: {
        type: Number,
        required: false,
        default: 0
      },
      image: {
        type: String,
        required: true
      },
      text: {
        type: String,
        required: true
      },
      track: {
        type: String,
        required: true
      }
    },
    methods: {
      goTo() {
        this.$router.push('/track/' + this.track)
      }
    }
  })
</script>

<style scoped lang="scss">
  .directionCard {
    cursor: pointer;
    display: inline-flex;
    width: 100%;
    height: 100%;
    div {
      width: 100%;
      display: flex;
      text-align: center;
      flex-direction: column;
      img {
        display: block;
        height: auto;
        border: 4px solid $secondary-color-dark;
        border-radius: 4px;
        padding: 4px;
        box-shadow: 2px 3px 5px rgba(0, 0, 0, 0.2);
      }
      span {
        display: block;
        color: $primary-color-dark;
        font-size: 18px;
        font-weight: 600;
        font-family: 'Montserrat';
        margin-top: 16px;
        letter-spacing: 0.04em;
        text-decoration: underline;
        text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
        @media (max-width: $medium) {
          margin-bottom: 24px;
        }
      }
    }
    @media (min-width: $medium) {
      width: 50%;
    }
    @media (min-width: $large) {
      width: 20%;
    }
  }
</style>
