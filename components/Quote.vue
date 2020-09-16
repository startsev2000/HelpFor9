<template>
  <div class="quote d-flex flex-row">
    <svg class="left-bracket" width="25" height="70" viewBox="0 0 27 112" fill="none" xmlns="http://www.w3.org/2000/svg">
      <g filter="url(#filter0_d)">
        <path d="M2.6084 0.380005H20.3184V5.11H8.10839V98.61H20.3184V103.34H2.6084V0.380005Z" :fill="color"/>
      </g>
      <defs>
        <filter id="filter0_d" x="0.608398" y="0.380005" width="25.71" height="110.96" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
          <feFlood flood-opacity="0" result="BackgroundImageFix"/>
          <feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"/>
          <feOffset dx="2" dy="4"/>
          <feGaussianBlur stdDeviation="2"/>
          <feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.1 0"/>
          <feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow"/>
          <feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow" result="shape"/>
        </filter>
      </defs>
    </svg>
    <p><slot></slot></p>
    <svg class="right-bracket" width="25" height="70" viewBox="0 0 27 112" fill="none" xmlns="http://www.w3.org/2000/svg">
      <g filter="url(#filter0_d)">
        <path d="M24.3916 103.62H6.6816V98.89H18.8916L18.8916 5.39002H6.6816L6.6816 0.660019H24.3916L24.3916 103.62Z" :fill="color"/>
      </g>
      <defs>
        <filter id="filter0_d" x="0.681641" y="0.660034" width="25.71" height="110.96" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
          <feFlood flood-opacity="0" result="BackgroundImageFix"/>
          <feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"/>
          <feOffset dx="-2" dy="4"/>
          <feGaussianBlur stdDeviation="2"/>
          <feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.1 0"/>
          <feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow"/>
          <feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow" result="shape"/>
        </filter>
      </defs>
    </svg>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    name: "Quote",
    props: {
      color: {
        type: String,
        required: false,
        default: '#DC642C'
      }
    }
  })
</script>

<style scoped lang="scss">
  .quote {
    p {
      max-width: 90%;
      text-align: center;
      width: auto;
      margin: auto 32px;
      font-size: 18px;
      font-weight: 600;
      font-family: 'Montserrat';
      letter-spacing: 0.15em;
    }
    .left-bracket {
      margin-left: 0;
    }
    .right-bracket {
      margin-right: 0;
      margin-left: auto;
    }
  }
</style>
