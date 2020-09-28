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

        <div class="facts1">
          <li class="fact1" v-if="track === 'mathinfo'">Мореееееее программирования!</li>
          <li class="fact2" v-if="track === 'mathinfo'">Направление, которое занимает очень много времени</li>
          <li class="fact3" v-if="track === 'mathinfo'">Решение уравнений в целых числах необычным способом</li>
          <li class="fact4" v-if="track === 'mathinfo'">Очень сильная математика</li>
          <li class="fact5" v-if="track === 'mathinfo'">Шутки про программистов!</li>

          <li class="fact1" v-if="track === 'mathec'">Тяжело, но приятно)))</li>
          <li class="fact2" v-if="track === 'mathec'">Лучшие люди, лучшее здание!</li>
          <li class="fact3" v-if="track === 'mathec'">Много математики, много экономики</li>
          <li class="fact4" v-if="track === 'mathec'">Куча дедлайнов и мало сна:) но оно того стоит!</li>

          <li class="fact1" v-if="track === 'socec'">Милые и дружелюбные ребята</li>
          <li class="fact2" v-if="track === 'socec'">Вечная конкуренция за возможность вставить слово</li>
          <li class="fact3" v-if="track === 'socec'">У - универсальность</li>
          <li class="fact4" v-if="track === 'socec'">Много обществознания</li>
          <li class="fact5" v-if="track === 'socec'">Ботать и тащить олимпиады</li>
          <li class="fact6" v-if="track === 'socec'">Трата времени неконтролируемо и беспощадно</li>
          <li class="fact7" v-if="track === 'socec'">СЕМЬЯ!</li>

          <li class="fact1" v-if="track === 'hum'">Вечные шутки Базарова</li>
          <li class="fact2" v-if="track === 'hum'">Это бывшие дизайнеры</li>
          <li class="fact3" v-if="track === 'hum'">Литературные шутки, которые никто не понимает</li>
          <li class="fact4" v-if="track === 'hum'">Самые разнообразные творческие люди</li>

          <li class="fact1" v-if="track === 'design'">Бесконечный творческий хаос</li>
          <li class="fact2" v-if="track === 'design'">Вечная подготовка к просмотру</li>
          <li class="fact3" v-if="track === 'design'">Н - нестандартность!</li>

          <li class="fact1" v-if="track === 'law'">Сложная матеша и легкое право</li>
          <li class="fact2" v-if="track === 'law'">Шутки о российском законодательстве</li>
          <li class="fact3" v-if="track === 'law'">Семья, в которой постоянно спорят</li>
          <li class="fact4" v-if="track === 'law'">Сборище политиков</li>
          <li class="fact5" v-if="track === 'law'">Серьёзные люди с кодексами</li>

          <li class="fact1" v-if="track === 'oriental'">Восточная любовь, уютный бот и тепло</li>
          <li class="fact2" v-if="track === 'oriental'">Атмосфера тепла и любви</li>
          <li class="fact3" v-if="track === 'oriental'">Уют и ламповость</li>
          <li class="fact4" v-if="track === 'oriental'">Самый теплый коллектив</li>
          <li class="fact5" v-if="track === 'oriental'">Когда ты начинаешь предложение на русском и заканчиваешь на арабском:)</li>

          <li class="fact1" v-if="track === 'psysoc'">Психоанализы по Свинке Пеппе:)</li>
          <li class="fact2" v-if="track === 'psysoc'">Психология - это всё по Фрейду</li>
          <li class="fact3" v-if="track === 'psysoc'">Микроскопы</li>
          <!--<div class="imgs">
            <img class="image" v-if="track === 'design'" src="/img/ui/factpages/facts_design.svg">
            <img class="image" v-if="track === 'psysoc'" src="/img/ui/factpages/facts_psysoc.svg">
            <img class="image" v-if="track === 'oriental'" src="/img/ui/factpages/facts_oriental.svg">
          </div>-->
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
      @media (max-width: $large) {
        height: 50%;
        width: auto;
      }
    }
    .right-blot {
      position: absolute;
      height: 100%;
      width: auto;
      left: auto;
      right: 0;
      top: 0; 
      @media (max-width: $large) {
        height: 50%;
        width: auto;
      }
    }
    .facts1 {
      font-size: 28px;
      font-family: 'Montserrat';
      margin-bottom: -10px;
      padding-left: 2px;
      .image {
        margin: auto;
      }
      .fact1 {
        list-style-image: url('/img/ui/factpages/num1.svg');
        padding-left: 2px;
      }
      .fact2 {
        list-style-image: url('/img/ui/factpages/num2.svg');
        padding-left: 2px;
      }
      .fact3 {
        list-style-image: url('/img/ui/factpages/num3.svg');
        padding-left: 2px;
      }
      .fact4 {
        list-style-image: url('/img/ui/factpages/num4.svg');
        padding-left: 2px;
      }
      .fact5 {
        list-style-image: url('/img/ui/factpages/num5.svg');
        padding-left: 2px;
      }
      .fact6 {
        list-style-image: url('/img/ui/factpages/num6.svg');
        padding-left: 2px;
      }
      .fact7 {
        list-style-image: url('/img/ui/factpages/num7.svg');
        padding-left: 2px;
      }
      .fact8 {
        list-style-image: url('/img/ui/factpages/num8.svg');
        padding-left: 2px;
      }
      @media (max-width: $large) {
        font-size: 18px;
      }
    }
    .imgs {
      position: absolute;
      left: 500px;
      bottom: 200px;
      display: inline;
      padding: 0;
      margin: 0;
      @media (max-width: $large) {
        left: 300px;
        bottom: 40px;
        height: 80%;
        width: 80%;
      }
    }

</style>
