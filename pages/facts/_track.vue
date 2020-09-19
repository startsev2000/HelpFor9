<template>
  <div class="facts">
    <div v-if="available">
      <div>
        <img class="left-blot" src="/img/ui/blots/blot_left_2.svg">
        <img class="right-blot" src="/img/ui/blots/blot_right_2.svg"> 
        <div class="header">
          <span class="name">Что такое {{ tracksAvailable[trackName] }}?</span>
        </div>
      </div>
    </div>
    <div v-else class="not-available container d-flex">
      <div style="margin: auto; position: relative;">
        <p class="foreground-text">
          Факты & советы<br>здесь скоро появятся :)
        </p>
        <p class="background-text">
          Факты & советы<br>здесь скоро появятся :)
        </p>
        <p class="transparent-text">
          Факты & советы<br>здесь скоро появятся :)
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    name: "Facts",
    validate({ params }): boolean {
      const available: Array<String> = [
        'mathinfo', 'mathec', 'math', 'socec', 'hum', 'design', 'oriental', 'psysoc', 'law', 'sci'
      ]
      if (!Object.keys(params).includes('track')) {
        return false
      }
      return available.includes(params.track)
    },
    data() {
      return {
        track: '' as string,
        tracksAvailable: [
          'hum', 'oriental', 'psysoc', 'design', 'mathec', 'socec', 'mathinfo', 'law'
        ] as Array<String>
      }
    },
    computed: {
      available(): boolean {
        return this.tracksAvailable.includes(this.track)
      }
    },
    mounted() {
      this.track = this.$route.params.track
    }
  })
</script>

<style scoped lang="scss">
  .not-available {
    height: 100vh;
    .transparent-text {
      color: transparent;
    }
    .foreground-text {
      position: absolute;
      color: $header-color;
    }
    .background-text {
      position: absolute;
      color: transparent;
      transform: translate(4px, -4px);
      -webkit-text-stroke: 1px $header-color;
      @media (max-width: $large) {
        display: none;
      }
    }
    p {
      font-size: 84px;
      text-align: center;
      font-weight: bold;
      font-family: 'Montserrat';
      @media (max-width: $large) {
        font-size: 42px;
      }
    }
  }
</style>
