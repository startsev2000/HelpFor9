<template>
  <div class="track-description">
    <LinePattern :pattern="fullPatternPath" />
    <div class="container">
      <p class="text-description">
        <slot></slot>
      </p>
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'
  import LinePattern from '~/components/LinePattern.vue'
  import LyceumTrackObject from '~/assets/global'

  export default Vue.extend({
    name: "TrackDescription",
    components: {
      LinePattern
    },
    props: {
      track: {
        type: String,
        required: true
      }
    },
    data() {
      return {
        linePattern: {
          root: '/img/ui/linepattern/',
          patterns: {
            'mathinfo': 'mathinfo_blue',
            'mathec': 'mathec_orange',
            'math': 'math',
            'socec': 'socec_yellow',
            'hum': 'hum_orange',
            'design': 'design_blue',
            'oriental': 'oriental_orange',
            'psysoc': 'psysoc',
            'law': 'law',
            'sci': 'sci_orange'
          } as LyceumTrackObject<string>
        }
      }
    },
    /*computed: {
      fullPatternPath(): string {
        return this.linePattern.root + this.linePattern.patterns[this.track] + '.svg'
      }
    }
    */
  })
</script>

<style scoped lang="scss">
  .track-description {

  }
  .text-description {
    width: 100%;
    margin: 64px 0;
    text-align: center;
    font-size: 18px;
    font-weight: 600;
    font-family: 'Montserrat';
    letter-spacing: 0.15em;
  }
</style>
