<template>
  <div class="facts">
    <img class="left-blot" src="/img/ui/blots/blot_left_4.svg">
    <img class="right-blot" src="/img/ui/blots/blot_right_4.svg"> 
    <div v-if="available" class="available container d-flex">   
      <div class="header">

        <p class="foreground-text" v-if="track === 'mathinfo'" >Что такое матинфо?</p>
        <p class="background-text" v-if="track === 'mathinfo'" >Что такое матинфо?</p>
        <p class="transparent-text" v-if="track === 'mathinfo'" >Что такое матинфо?</p>

        <p class="foreground-text" v-if="track === 'mathec'" >Что такое матэк?</p>
        <p class="background-text" v-if="track === 'mathec'" >Что такое матэк?</p>
        <p class="transparent-text" v-if="track === 'mathec'" >Что такое матэк?</p>

        <p class="foreground-text" v-if="track === 'socec'" >Что такое соцэк?</p>
        <p class="background-text" v-if="track === 'socec'" >Что такое соцэк?</p>
        <p class="transparent-text" v-if="track === 'socec'" >Что такое соцэк?</p>

        <p class="foreground-text" v-if="track === 'hum'" >Что такое гум?</p>
        <p class="background-text" v-if="track === 'hum'" >Что такое гум?</p>
        <p class="transparent-text" v-if="track === 'hum'" >Что такое гум?</p>

        <p class="foreground-text" v-if="track === 'design'" >Что такое дизайн?</p>
        <p class="background-text" v-if="track === 'design'" >Что такое дизайн?</p>
        <p class="transparent-text" v-if="track === 'design'" >Что такое дизайн?</p>

        <p class="foreground-text" v-if="track === 'law'" >Что такое юр?</p>
        <p class="background-text" v-if="track === 'law'" >Что такое юр?</p>
        <p class="transparent-text" v-if="track === 'law'" >Что такое юр?</p>

        <p class="foreground-text" v-if="track === 'oriental'" >Что такое восток?</p>
        <p class="background-text" v-if="track === 'oriental'" >Что такое восток?</p>
        <p class="transparent-text" v-if="track === 'oriental'" >Что такое восток?</p>

        <p class="foreground-text" v-if="track === 'psysoc'" >Что такое психология?</p>
        <p class="background-text" v-if="track === 'psysoc'" >Что такое психология?</p>
        <p class="transparent-text" v-if="track === 'psysoc'" >Что такое психология?</p>
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
  import LyceumTrackObject from '~/assets/global.ts'
  
  interface TrackDepartmentName {
    names: LyceumTrackObject<string>
  }

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
        ] as Array<String>,
        titles: [
          {'mathinfo': 'Матинфо'},
          {'hum': 'Гум'},
          {'mathec': 'Матэк'},
          {'oriental': 'Восток'},
          {'psysoc': 'Психология'}, 
          {'design': 'Дизайн'},
          {'socec': 'Соцэк'},
          {'law': 'Юр'}
        ]
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
  .not-available, .available {
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
  .available {
    position: relative;
    padding: 0;
    .header {
      position: relative;
      width: 90%;
      margin: 0 auto;
      padding-top: 32px;
        span {
          color: $header-color;
          width: fit-content;
          display: block;
          font-size: 80px;
          font-weight: 700;
          font-family: 'IBM Plex Sans';
          margin-top: 96px;
          margin-left: 36px;
          -webkit-text-stroke: 1px $header-color;
          @media (max-width: $large) {
            font-size: 24px;
            font-weight: 200;
            color: $header-color;
            font-family: 'IBM Plex Sans';
            -webkit-text-stroke: 1px $header-color;
          } 
        }
      }
      .mind {
        span {
          color: transparent;
          font-size: 48px;
          font-weight: 700;
          font-family: 'IBM Plex Sans';
        }
      }
    }
      .footer {
        margin-top: 32px;
        margin-bottom: 64px;
      }
    .small-header {
      width: 60% !important;
    }
    .track-head-menu {
      position: absolute;
      left: auto;
      right: 48px;
      top: 48px;
    }
    .left-blot {
      position: absolute;
      height: 100%;
      width: auto;
      margin-bottom: 40px;
      margin-top: -20px;
      
    }
    .right-blot {
      position: absolute;
      height: 100%;
      width: auto;
      left: auto;
      right: 0;
      top: 0; 
    }

</style>
