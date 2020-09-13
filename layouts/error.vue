<template>
  <div class="error container d-flex">
    <div class="int-block d-flex flex-column">
      <div class="head d-flex">
        <img src="/img/ui/error.svg">
        <span>ERROR {{ error.statusCode }}</span>
      </div>
      <p class="sub">
        {{ sub }}
      </p>
      <p class="description">
        {{ description }}
      </p>
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue';

  export default Vue.extend({
    name: "error",
    props: ['error'],
    /*
    computed: {
      sub: function() {
        if (Object.keys(this.subs).includes("" + this.error.statusCode)) {
          return this.subs[this.error.statusCode]
        } else {
          return this.subs.default
        }
      },
      description: function() {
        if (Object.keys(this.descriptions).includes("" + this.error.statusCode)) {
          return this.descriptions[this.error.statusCode]
        } else {
          return this.descriptions.default
        }
      }
    },
    */
    data() {
      return {
        subs: {
          "404": 'Page not found',
          "500": 'Internal server error',
          "default": ''
        },
        descriptions: {
          "404": 'Такое иногда случается. Самые вероятные причины - устаревшая ссылка или данная страница была удалена автором.',
          "default": ''
        }
      }
    }
  })
</script>

<style scoped lang="scss">
  .error {
    height: 100vh;
    .int-block {
      width: 100%;
      margin: auto 15px;
      .head {
        margin: auto auto;
        img {
          display: inline;
          width: 128px;
          margin: auto 0;
          @media (max-width: $small) {
            width: 60%;
            margin: 0 auto;
          }
        }
        span {
          margin: auto 0 auto 32px;
          font-style: normal;
          font-weight: normal;
          font-size: 72px;
          font-family: 'Montserrat';
          text-transform: capitalize;
          @media (max-width: $small) {
            font-size: 32px;
            margin: 0 auto;
          }
        }
        @media (max-width: $small) {
          flex-direction: column;
        }
      }
      .sub {
        color: rgba(0, 0, 0, 0.7);
        text-align: center;
        font-size: 32px;
        font-family: 'Montserrat';
        @media (max-width: $small) {
          font-size: 24px;
          margin: 12px 0 0;
        }
      }
      .description {
        margin: 32px 15% 0;
        color: rgba(0, 0, 0, 0.9);
        text-align: center;
        font-size: 28px;
        font-family: 'Montserrat';
        @media (max-width: $small) {
          font-size: 18px;
          margin: 24px 0 0;
        }
      }
    }
  }
</style>
