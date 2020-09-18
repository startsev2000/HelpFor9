<template>
  <div class="track-head">
    <img class="left-blot" src="/img/ui/blots/blot_left_2.svg">
    <img class="right-blot" src="/img/ui/blots/blot_right_2.svg">
    <TrackHeadMenu :track="trackName" />
    <div class="header" :class="{ 'small-header': isSmallHeader }">
      <div class="track-name">
        <span class="name1">{{ track.titles[trackName] }}</span>
        <span class="name2">{{ track.titles[trackName] }}</span>
        <span class="name3">{{ track.titles[trackName] }}</span>
      </div>
      <div class="mind">
        <span>{{ track.titles[trackName] }}</span>
        <TrackHeadMind
          :type="trackName"
          :text="track.minds[trackName]" />
      </div>
    </div>
    <div class="footer">
      <div class="container">
        <Quote :color="track.mainQuote.color[trackName]">
          {{ track.mainQuote.text[trackName] }}
        </Quote>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'
  import Quote from '~/components/Quote.vue'
  import TrackHeadMind from '~/components/track/TrackHeadMind.vue'
  import TrackHeadMenu from '~/components/track/TrackHeadMenu.vue'
  import LyceumTrackObject from '~/assets/global.ts'

  interface TrackDataObject {
    titles: LyceumTrackObject<string>,
    minds: LyceumTrackObject<string>,
    mainQuote: {
      text: LyceumTrackObject<string>,
      color: LyceumTrackObject<string>
    },
    smallHeader: Array<String>
  }

  export default Vue.extend({
    name: "TrackHead",
    components: {
      Quote,
      TrackHeadMind,
      TrackHeadMenu
    },
    props: {
      trackName: {
        type: String,
        required: true
      }
    },
    computed: {
      isSmallHeader(): boolean {
        return this.track.smallHeader.includes(this.trackName)
      }
    },
    data() {
      return {
        track: {
          titles: {
            'mathinfo': '⠀⠀⠀⠀Информатика и математика',
            'mathec': '⠀⠀⠀⠀Экономика и математика',
            'math': 'Математика⠀⠀⠀⠀⠀⠀',
            'socec': '⠀⠀⠀Экономика и \n социальные науки',
            'hum': 'Гуманитарные науки',
            'design': 'Дизайн⠀⠀⠀⠀⠀⠀⠀⠀⠀',
            'oriental': 'Востоковедение⠀⠀⠀',
            'psysoc': 'Психология⠀⠀⠀⠀⠀⠀⠀',
            'law': 'Юриспруденция⠀⠀⠀',
            'sci': 'Естественные науки'
          },
          minds: {
            'mathinfo': 'print: “Hello, world!”',
            'mathec': 'в LG нет FC;',
            'math': '',
            'socec': 'Социология, политология и экономика - это мой выбор',
            'hum': 'а... бэ... цэ... дэ...',
            'design': '',
            'oriental': '',
            'psysoc': '',
            'law': 'Протестую!',
            'sci': 'H-водород, O-кислород,\n С-углерод'
          },
          mainQuote: {
            text: {
              'mathinfo': 'ПИТОН, ПИТОН, ПИТОН, ПИТОН, ПИТОН, ПИТОН, ПИТОН, ПИТОН, ПИТОН, ПИТОН. Это был быстрый тест на то, программист ты или биолог.',
              'mathec': 'Отличить эндогенную переменную от экзогенной? Запросто!',
              'math': 'Нет, нет, здесь уже не просто «дважды два – четыре». Здесь всё намного серьёзнее, чем на любом другом направлении с профильной математикой.',
              'socec': 'Как говорят многие лицеисты в здании на Лялином переулке, и “соц”, и “эк”...',
              'hum': 'АЛЕКСАНДР СЕРГЕЕВИЧ. АЛЕКСАНДР СЕРГЕЕВИЧ. АЛЕКСАНДР СЕРГЕЕВИЧ. Это был быстрый тест на то, пушкинист ты или просто знаешь имя и отчество Грибоедова.',
              'design': 'Мастихин, разбавитель, масленка – для тебя это не просто набор слов, а предметы первой необходимости. (Ну или ты просто рисуешь на графическом планшете)',
              'oriental': '«师傅领进门, 修 行在自身». Учитель только подводит к двери, ученик сам проходит через неё.',
              'psysoc': 'Я являюсь психологом только в чужой жизни, в своей – я психопат…',
              'law': 'Расследование уголовных дел, детективы, судебные процессы. Почти как в кино...',
              'sci': 'Если ты знаешь, какое вещество выпадает в осадок, если смешать растворы нитрата бария и серной кислоты, или можешь с легкостью объяснить закон всемирного тяготения, то ты выбрал правильное направление.'
            },
            color: {
              'mathinfo': '#7CA75C',
              'mathec': '#7CA75C',
              'math': '#6EA763',
              'socec': '#96B67E',
              'hum': '#DC642C',
              'design': '#F78B59',
              'oriental': '#6EA763',
              'psysoc': '#6EA763',
              'law': '#F78B59',
              'sci': '#6EA763'
            }
          },
          smallHeader: ['hum', 'law', 'design', 'oriental', 'math', 'psysoc', 'sci']
        } as TrackDataObject
      }
    }
  })
</script>

<style scoped lang="scss">
  .track-head {
    position: relative;
    padding: 0;
    .header {
      position: relative;
      width: 90%;
      margin: 0 auto;
      padding-top: 32px;
      .track-name {
        span {
          color: transparent;
          width: fit-content;
          display: block;
          font-size: 44px;
          font-weight: 700;
          font-family: 'IBM Plex Sans';
          margin-top: -12px;
          -webkit-text-stroke: 1px $header-color;
          @media (max-width: $large) {
            font-size: 24px;
            font-weight: 200;
            color: $header-color;
            font-family: 'IBM Plex Sans';
            -webkit-text-stroke: 1px $header-color;
            
        } 
        }
        span:first-child {
          margin-top: 0;
          @media (max-width: $large) {
            display: none;
         } 
        }
        span:last-child {
          color: $header-color;
          -webkit-text-stroke-width: 0;
          @media (max-width: $large) {
            display: none;
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
      height: 60%;
      width: auto;
      margin-bottom: 40px;
      margin-top: -20px;
      @media (max-width: $large) {
          display: none;
      } 
      
    }
    .right-blot {
      position: absolute;
      height: 60%;
      width: auto;
      left: auto;
      
      right: 0;
      top: 0;
      @media (max-width: $large) {
          display: none;
      } 
    }
  }
</style>
