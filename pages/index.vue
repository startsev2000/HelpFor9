<template>
  <div class="main">
    <div class="container-xl" style="margin-top: 64px;">
      <div class="row">
        <div class="col-12 d-flex d-lg-none">
          <img src="/img/ui/lyceum_logo.png" class="lyceumLogo">
        </div>
        <div class="col-12 col-lg-5 d-flex">
          <ButtonSecondary class="upperButton"><a href="https://vk.com/lycsovet">Совет Лицеистов</a>
          </ButtonSecondary>
        </div>
        <div class="d-none col-lg-2 d-lg-flex">
          <img src="/img/ui/lyceum_logo.png" class="lyceumLogo">
        </div>
        <div class="col-12 col-lg-5 d-block d-lg-flex">
          <div class="lowerRow">
            <ButtonSecondary class="lowerButton">
              Факультативы (soon)
            </ButtonSecondary>
            <ButtonSecondary class="lowerButton" style="margin-left: 12px;">
              HelpFor9
            </ButtonSecondary>
          </div>
        </div>
      </div>
      <div style="position: relative;">
        <img class="d-none d-lg-block plane" src="/img/ui/plane.png" >
        <p class="mainDescription">
          Мы поможем тебе определиться<br>с направлением дальнейшего образования
        </p>
      </div>
      <div style="width: 100%; display: flex; flex-wrap: wrap; margin-bottom: 8vh;">
        <DirectionCard
          track="mathinfo"
          text="Информатика, инженерия и математика"
          image="/img/ui/main/mathinfo.png" />
        <DirectionCard
          :type="1"
          track="psysoc"
          text="Психология"
          image="/img/ui/main/psychology.png" />
        <DirectionCard
          track="law"
          text="Юриспруденция"
          image="/img/ui/main/lawstudies.png" />
        <DirectionCard
          :type="1"
          track="design"
          text="Дизайн"
          image="/img/ui/main/design.png" />
        <DirectionCard
          track="hum"
          text="Гуманитарные науки"
          image="/img/ui/main/humscience.png" />
        <DirectionCard
          :type="1"
          track="math"
          text="Математика"
          image="/img/ui/main/math.png" />
        <DirectionCard
          :type="2"
          track="sci"
          text="Естественные науки"
          image="/img/ui/main/chembio.png" />
        <DirectionCard
          :type="1"
          track="oriental"
          text="Востоковедение"
          image="/img/ui/main/eaststudies.png" />
        <DirectionCard
          :type="2"
          track="mathec"
          text="Экономика и математика"
          image="/img/ui/main/mathec.png" />
        <DirectionCard
          :type="1"
          track="socec"
          text="Экономика и социальные науки"
          image="/img/ui/main/socec.png" />
      </div>
    </div>
    <LinePattern pattern="/img/ui/linepattern/futuritet.svg" />
    <div style="position: relative;">
      <img class="leftBlot d-none d-xl-block" src="/img/ui/blots/blot_left_1.svg">
      <img class="rightBlot d-none d-xl-block" src="/img/ui/blots/blot_right_1.svg">
      <div class="container text-center greeting" style="padding: 24px 0;">
        <div class="d-flex">
          <div class="d-flex" style="margin: 0 auto; max-width: 810px;">
            <p class="d-inline-block">Привет, девятиклассники!</p>
            <img class="d-inline-block" style="margin: auto 0 auto 12px;" src="/img/ui/head.png">
          </div>
        </div>
        <p>
          Будущее и время - вот чем вы управляете, поэтому направление и назвали «Футуритет». Сейчас вы находитесь на отправной точке, впереди десять дорог, десять вариантов обучения. Вам предстоит нелегкий выбор, и мы хотим помочь.
        </p>
        <p>
          На данный момент вы можете вкратце ознакомиться с направлениями. В скором времени здесь появится много всего нового интересного.
        </p>
        <p>Искренне ваш, первый и второй выпуск Футуритета</p>
        <p>Есть вопросы или предложения? Нашли баги на сайте? Пишите <a href="https://vk.com/hsehelpfor9">сюда</a>.</p>
      </div>
    </div>
    <LinePattern pattern="/img/ui/linepattern/futuritet.svg" style="margin-bottom: 20vh;" />
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'
  import ButtonSecondary from '~/components/button/ButtonSecondary.vue'
  import LinePattern from '~/components/LinePattern.vue'
  import DirectionCard from '~/components/DirectionCard.vue'

  export default Vue.extend({
    components: {
      ButtonSecondary,
      LinePattern,
      DirectionCard
    }
  })
</script>

<style scoped lang="scss">
  .lyceumLogo {
    height: 64px;
    margin: 0 auto;
    filter: drop-shadow(3px 3px 5px rgba(0, 0, 0, 0.1));
    @media (max-width: $large) {
      margin: 0 auto 32px;
    }
  }
  .mainDescription {
    padding: 8vh 10%;
    text-align: center;
    font-size: 32px;
    font-weight: 500;
    font-family: 'Roboto Slab';
  }
  .upperButton {
    margin: auto auto auto 0;
    width: fit-content;
    @media (max-width: $large) {
      width: 100%;
      text-align: center;
    }
  }
  .lowerRow {
    margin: auto 0 auto auto;
    .lowerButton {
      width: fit-content;
      @media (max-width: $large) {
        margin: 12px 0 0 !important;
        width: 100%;
        text-align: center;
      }
    }
    @media (max-width: $large) {
      margin: 0 !important;
    }
  }
  .greeting {
    p {
      max-width: 810px;
      margin: 32px auto;
      padding: 0 24px;
      font-size: 18px;
      font-weight: 500;
      font-family: 'Montserrat';
    }
  }
  .plane {
    position: absolute;
    height: 64px;
    top: 64px;
    left: auto;
    bottom: auto;
    right: 32px;
  }
</style>
