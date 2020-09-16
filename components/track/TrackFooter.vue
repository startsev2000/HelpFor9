<template>
  <div class="track-footer">
    <LinePattern :pattern="fullPatternPath" />
    <div v-if="track !== ''" class="container" style="margin-top: 64px;">
      <Quote>
        {{ content[track].text }}
      </Quote>
    </div>
    <div v-if="renderAvailable && content[trackName].image != null" class="d-flex">
      <div
        class="footer-image-full"
        v-if="content[trackName].image.position === Position.Full"
        :style="'background-image: url(' + content[trackName].image.src + ')'">
      </div>
      <img
        class="footer-image-center"
        v-else-if="content[trackName].image.position === Position.Center"
        :src="content[trackName].image.src">
    </div>
    <div v-else style="height: 64px;"></div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'
  import Quote from '~/components/Quote.vue'
  import LinePattern from '~/components/LinePattern.vue'
  import LyceumTrackObject from '~/assets/global'

  enum Position { None, Full, Center }

  interface FooterContent {
    text: string,
    image: {
      src: string,
      position: Position
    } | null
  }

  export default Vue.extend({
    name: "TrackFooter",
    components: {
      Quote,
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
        Position,
        trackName: '',
        renderAvailable: false,
        linePattern: {
          root: '/img/ui/linepattern/',
          patterns: {
            'mathinfo': 'mathinfo_green',
            'mathec': 'mathec_green',
            'math': 'math',
            'socec': 'socec_green',
            'hum': 'hum_blue',
            'design': 'design_green',
            'oriental': 'oriental_blue',
            'psysoc': 'psysoc',
            'law': 'law',
            'sci': 'sci_green'
          } as LyceumTrackObject<string>
        },
        content: {
          'mathinfo': {
            text: 'Направление математика, инженерия и математика подойдет для всех ребят, кто хочет общаться с компьютером (и не только) на “ты”!',
            image: null
          },
          'mathec': {
            text: 'Нашел что-то для себя? Тогда на матэке тебя уже ждут!',
            image: null
          },
          'math': {
            text: 'Чтобы лучше познать точные науки, формируются маленькие профильные группы, в которых преподают несколько учителей. Для тех, кто хочет совершенствовать свои знания есть олимпиадные факультативы, еще одна крутая особенность данного направления - возможность посещать факультет математики НИУ ВШЭ.',
            image: {
              src: '/img/ui/trackfooter/math.png',
              position: Position.Full
            }
          },
          'socec': {
            text: 'И “соц” и “эк”, как иногда говорят лицеисты, на этом направлении ты сможешь выбрать обширный учебный план и взять  частичку как от социальных наук, так и от технических. Думаю, ты уже знаешь, что взять, поэтому до встречи в новом году!',
            image: null
          },
          'hum': {
            text: 'Книги, поэты, писатели, культура... Звучит заманчиво, не правда ли?',
            image: {
              src: '/img/ui/trackfooter/hum.png',
              position: Position.Center
            }
          },
          'design': {
            text: 'Ну что, ты готов пополнить наши ряды? Тогда мы ждем тебя у нас на направлении!',
            image: {
              src: '/img/ui/trackfooter/design.png',
              position: Position.Center
            }
          },
          'oriental': {
            text: 'А ты готов оседлать дракона и пойти изучать страны Востока?',
            image: {
              src: '/img/ui/trackfooter/oriental.png',
              position: Position.Center
            }
          },
          'psysoc': {
            text: 'Неплохо иметь друга психолога (во всех смыслах этого слова). Но еще лучше, когда ты психолог сам. Присоединяйся к нам!',
            image: {
              src: '/img/ui/trackfooter/psysoc.png',
              position: Position.Center
            }
          },
          'law': {
            text: 'Наверное, каждый когда-либо смотрел сериал про грабителя и следователя. Загадки, улики, экспертизы — все это так захватывало дух. После окончания нашего направления героем такого сериала сможешь стать и ты! Здесь ты точно не заскучаешь!',
            image: null
          },
          'sci': {
            text: 'Лабораторные опыты, которые проводят ребята этого направления, любят абсолютно все! Когда еще можно будет наткнуться на захватывающие видео в инстаграме...',
            image: null
          }
        } as LyceumTrackObject<FooterContent>
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
    },
    
    watch: {
      track(newValue: string, oldValue: string): void {
        this.renderAvailable = newValue !== ''
        this.trackName = newValue
      }
    }
  })
</script>

<style scoped lang="scss">
  .footer-image-full {
    margin: 64px 0 0;
    width: 100%;
    height: 150px;
    background-size: auto 100%;
    background-repeat: repeat-x;
  }
  .footer-image-center {
    margin: 0 auto;
    max-width: 100%;
    max-height: 300px;
  }
</style>
