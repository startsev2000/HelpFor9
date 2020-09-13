<template>
  <div class="track-head-mind">
    <span>{{ text }}</span>
    <img :src="path">
  </div>
</template>

<script lang="ts">
  import Vue from 'vue';

  export default Vue.extend({
    name: 'TrackMind',
    props: {
      type: {
        type: String,
        required: false,
        default: 'default'
      },
      text: {
        type: String,
        required: false,
        default: ''
      }
    },
    data() {
      return {
        root: '/img/ui/trackman/' as string,
        uniqueImages: ['design', 'math', 'oriental', 'psysoc'] as Array<String>
      }
    },
    computed: {
      path(): string {
        let result: string

        if (this.uniqueImages.includes(this.type)) {
          result = this.root + this.type + '.png'
        } else {
          result = this.root + 'default.png'
        }

        return result
      }
    }
  })
</script>

<style scoped lang="scss">
  .track-head-mind {
    position: relative;
    display: inline-block;
    img {
      width: 250px;
    }
    span {
      white-space: pre-wrap;
      width: fit-content;
      position: absolute;
      left: 100px;
      top: -30px;
      text-align: center;
      font-weight: 500;
      font-family: 'Montserrat';
      transform: rotate(-10deg);
    }
  }
</style>
