<template>
  <div class="track-head-menu">
    <div class="menu">
      <div
        :key="index"
        v-for="(link, index) in menuLinks"
        class="item">
        <a :href="applyPattern(link.pattern)">{{ link.text }}</a>
        <img src="/img/ui/separator.svg" class="separator">
      </div>
    </div>
    <img :src="logoPath">
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  interface MenuLink {
    text: string,
    pattern: string
  }

  interface URLPattern {
    name: string,
    value: string
  }

  export default Vue.extend({
    name: "TrackHeadMenu",
    props: {
      track: {
        type: String,
        required: true
      }
    },
    data() {
      return {
        trackLogoRoot: '/img/ui/tracklogo/' as string,
        menuLinks: [
          /*{
            text: 'календарь событий',
            pattern: '/calendar/{track}'
          },*/
          {
            text: '',
            pattern: '/contacts',
          }
        ] as Array<MenuLink>
      }
    },
    computed: {
      logoPath(): string {
        return this.trackLogoRoot + this.track + '.png'
      }
    },
    methods: {
      applyPattern(url: string): string {
        return url.replace('{track}', this.track)
      }
    }
  })
</script>

<style scoped lang="scss">
  .track-head-menu {
    display: flex;
    flex-direction: row;
    * {
      margin-top: auto;
      margin-bottom: auto;
    }
    img {
      height: 64px;
    }
    .menu {
      display: flex;
      margin-right: 48px;
      * {
        margin-top: auto;
        margin-bottom: auto;
      }
      .item {
        display: inline-flex;
        * {
          margin-top: auto;
          margin-bottom: auto;
        }
        a {
          color: black;
          font-size: 13px;
          font-weight: 600;
          font-family: 'Montserrat';
          //text-transform: lowercase;
        }
        .separator {
          height: 10px;
          margin: auto 18px;
        }
      }
      .item:last-of-type {
        .separator {
          display: none;
        }
      
      }
      @media (max-width: $large) {
            display: none;
         } 
      }
    }
  
</style>
