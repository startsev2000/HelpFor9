<template>
  <div v-if="blockAvailable[track]" class="track-fact">
    <LinePattern :pattern="fullPatternPath" />
    <div class="fact-content">
      <div class="container">
        <p class="fact-text">
          {{ content[track].text }}
        </p>
        <img
          v-if="content[track].image != null"
          class="fact-image"
          :src="content[track].image">
      </div>
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'
  import LinePattern from '~/components/LinePattern.vue'
  import LyceumTrackObject from '~/assets/global'

  interface FactContent {
    text: string,
    image: string | null
  }

  export default Vue.extend({
    name: "TrackFact",
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
        blockAvailable: {
          'mathinfo': true,
          'mathec': true,
          'math': false,
          'socec': false,
          'hum': true,
          'design': true,
          'oriental': true,
          'psysoc': false,
          'law': false,
          'sci': false
        } as LyceumTrackObject<boolean>,
        content: {
          'mathinfo': {
            text: 'Все стремительнее набирает силу олимпиадное движение. Самый распространённый предмет – конечно, информатика. Можно готовиться самому, но в лицее есть и факультатив по подготовке к олимпиадам.',
            image: '/img/ui/trackfact/mathinfo.png'
          },
          'mathec': {
            text: 'Чтобы повысить шанс успеха, Матэк отправляет ребят на выездные экономические школы. Это «места тусовки экономистов». В лицее ребята встречаются на факультативах, на курсах по подготовке к олимпиадам и на парах. Здесь можно и найти себе компанию, и попросить совет.',
            image: '/img/ui/trackfact/mathec.png'
          },
          'math': {
            text: 'В этом году вся математическая семья переезжает в здание на Колобке. Ученики Футуритета смогут пообщаться со старшеклассниками нашего направления и найти своих будущих друзей. ',
            image: null
          },
          'socec': {
            text: 'Атмосфера соцэка пропитана многообразием интересов. Лицеисты стараются узнать максимум по каждому предмету, а многообразие увлечений и занятий делает насыщенной социальную жизнь направления. ',
            image: null
          },
          'hum': {
            text: 'На БХ ты услышишь цитаты из Маяковского и Достоевского, окунешься в дискуссии на философские темы и найдешь людей, которые разбираются в нестандартных темах литературы и культурологии. Гуманитарное направление – это еще и уютные посиделки, концерты и поэтические вечера. Каждый день на лестничных пролетах появляются афиши, которые рассказывают о новом мероприятии.',
            image: null
          },
          'design': {
            text: 'Лицеисты на дизайне очень разноплановые, вместе с ними ты сможешь открыть для себя новые сферы дизайна и понять, в какой из них ты хочешь развиваться. Эти ребята всегда открыты к общению, они вдохновляют и мотивируют. На дизайне ты научишься экспериментировать и пробовать, а еще у тебя обязательно появится страничка в инстаграме, на которой ты будешь публиковать свои работы (если ее еще нет 😊).',
            image: '/img/ui/trackfact/design.png',
          },
          'oriental': {
            text: 'Лицеистов, которые учатся на этом направлении, называют «востоками». Кем же станут эти «востоки» в дальнейшем? Они будущие методисты, журналисты, переводчики, преподаватели и, пожалуй, просто самые загадочные ребята.',
            image: null
          },
          'psysoc': {
            text: 'Неплохо иметь друга психолога, но еще лучше, когда ты психолог сам!',
            image: null
          },
          'law': {
            text: 'Ребята с юриспруденции часто появляются в коридорах с конституцией в руках или устраивают мини-дебаты на «юридические» темы.',
            image: null
          },
          'sci': {
            text: 'У нас есть свои питомцы: лягушки и улитки. Они могут выслушать рассказы о твоих опытах и дать совет.',
            image: null
          },
        } as LyceumTrackObject<FactContent | null>
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
  .fact-content {
    margin: 64px 0;
  }
  .fact-text {
    width: 100%;
    text-align: center;
    font-size: 18px;
    font-weight: 600;
    font-family: 'Montserrat';
    letter-spacing: 0.15em;
  }
  .fact-image {
    width: 100%;
  }
</style>
