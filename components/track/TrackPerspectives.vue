<template>
  <div class="track-perspectives">
    <LinePattern :pattern="fullPatternPath" />
    <div>
      <img src="/img/ui/blots/blot_left_3.svg" alt="" class="leftBlot">
      <img src="/img/ui/blots/blot_right_3.svg" alt="" class="rightBlot">
      <div class="container main-content">
        <div class="row">
          <div class="col-12 col-md-4 fact-block">
            <img src="/img/ui/perspectives/1.png">
            <div>
              <!--<span>Учебный план</span>-->
              <p><a href="https://school.hse.ru">На сайте Лицея ты сможешь подробно рассмотреть учебный план на своем направлении</a></p>
            </div>
          </div>
          <!--<div class="col-12 col-md-4 fact-block">
            <img src="/img/ui/perspectives/2.png">
            <div>
              <span>Направление мечты</span>
              <p>IN DEVELOPMENT</p>
            </div>
          </div>-->
          <div class="col-12 col-md-4 fact-block">
            <img src="/img/ui/perspectives/3.png">
            <div>
              <!--<span>Факты и советы</span>-->
              <p v-if="track === 'mathinfo'"><a href='/facts/mathinfo'>Интересные факты про матинфо и советы от нынешних десятых</a></p>
              <p v-if="track === 'mathec'"><a href='/facts/mathec'>Интересные факты про матэк и советы от нынешних десятых</a></p>
              <p v-if="track === 'socec'"><a href='/facts/socec'>Интересные факты про соцэк и советы от нынешних десятых</a></p>
              <p v-if="track === 'hum'"><a href='/facts/hum'>Интересные факты про гум и советы от нынешних десятых</a></p>
              <p v-if="track === 'design'"><a href='/facts/design'>Интересные факты про дизайн и советы от нынешних десятых</a></p>
              <p v-if="track === 'law'"><a href='/facts/law'>Интересные факты про юр и советы от нынешних десятых</a></p>
              <p v-if="track === 'oriental'"><a href='/facts/oriental'>Интересные факты про восток и советы от нынешних десятых</a></p>
              <p v-if="track === 'psysoc'"><a href='/facts/psysoc'>Интересные факты про психологию и советы от нынешних десятых</a></p>
              <p v-if="track === 'math'"><a href='/facts/math'>Интересные факты про математику и советы от нынешних десятых</a></p>
              <p v-if="track === 'sci'"><a href='/facts/sci'>Интересные факты про ЕН и советы от нынешних десятых</a></p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'
  import LinePattern from '~/components/LinePattern.vue'
  import LyceumTrackObject from '~/assets/global'

  export default Vue.extend({
    name: 'TrackPerspectives',
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
        },
        link: {
          names: {
            'mathinfo': "https://school.hse.ru/math",
            'mathec': '',
            'math': '',
            'socec': '',
            'hum': '',
            'design': '',
            'oriental': '',
            'psysoc': '',
            'law': '',
            'sci': ''
          }
        }
      }
    },
    computed: {
      fullPatternPath(): any {
        if (this.track == 'mathinfo') {
          return this.linePattern.root + this.linePattern.patterns[this.track] + '.svg';
       }
       if (this.track == 'mathec') {
          return this.linePattern.root + this.linePattern.patterns[this.track] + '.svg';
       } 
       if (this.track == 'math') {
          return this.linePattern.root + this.linePattern.patterns[this.track] + '.svg';
       } 
       if (this.track == 'socec') {
          return this.linePattern.root + this.linePattern.patterns[this.track] + '.svg';
       } 
       if (this.track == 'hum') {
          return this.linePattern.root + this.linePattern.patterns[this.track] + '.svg';
       } 
       if (this.track == 'design') {
          return this.linePattern.root + this.linePattern.patterns[this.track] + '.svg';
       } 
       if (this.track == 'oriental') {
          return this.linePattern.root + this.linePattern.patterns[this.track] + '.svg';
       } 
       if (this.track == 'psysoc') {
          return this.linePattern.root + this.linePattern.patterns[this.track] + '.svg';
       } 
       if (this.track == 'law') {
          return this.linePattern.root + this.linePattern.patterns[this.track] + '.svg';
       } 
       if (this.track == 'sci') {
          return this.linePattern.root + this.linePattern.patterns[this.track] + '.svg';
       }
      }
    }
    
  })
</script>

<style scoped lang="scss">
  .track-perspectives {
    div {
      position: relative;
    }
  }
  .main-content {
    padding: 16px 4;
  }
  .fact-block {
    padding: 10px 160px !important;
    img {
      display: block;
      width: 137.17px;
      height: 142.61px;
      margin: 0 250%;
      @media (max-width: $large) {
          margin-left: -40px;
          margin-top: 10px;
        }
    }
    div {
      margin: 0 150%;
      padding: 4 36px;
      * {
        font-size: 18px;
        font-family: 'Montserrat';
      }
      /*span {
        position: absolute;
        width: 224px;
        height: 32px;
        font-weight: 700;
        line-height: 21px;
        display: flex;
        align-items: center;
        letter-spacing: 0.06em;
      }*/
      p {
        font-weight: 400;
        text-align: center;
        margin-left: 0px;
        width: 236px;
        height: 120px;
        top: 10px;
      }
      @media (max-width: $large) {
          margin-left: -90px;
          margin-top: 10px;
        }

    }
  }
  .leftBlot {
        @media (max-width: $large) {
          display: none;
      } 
      }
      .rightBlot {
        @media (max-width: $large) {
          display: none;
      } 
      }
</style>
