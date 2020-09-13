<template>
  <div class="loginPage">
    <div class="loginForm">
      <img class="plane" src="/img/ui/plane.png" />
      <h1>
        Добро пожаловать!<br>Пожалуйста, авторизуйтесь
      </h1>
      <div style="display: flex; flex-direction: column;">
        <TextInput
          style="margin: 0 auto; width: 80%;"
          logo="/img/logos/user.svg" />
        <PasswordInput style="margin: 16px auto; width: 80%;" />
        <div class="formFooter">
          <a href="#">Забыли пароль?</a>
          <ButtonPrimary style="display: inline; margin-left: 24px;">
            Войти
          </ButtonPrimary>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import TextInput from '../components/input/TextInput'
  import PasswordInput from '../components/input/PasswordInput'
  import ButtonPrimary from '../components/button/ButtonPrimary'

  export default {
    name: 'login',
    components: { ButtonPrimary, PasswordInput, TextInput }
  }
</script>

<style scoped lang="scss">
.loginPage {
  display: flex;
  height: 100vh;
  .loginForm {
    position: relative;
    margin: auto;
    padding: 32px 72px;
    background-color: $secondary-color;
    border-radius: 16px;
    box-shadow: 4px 4px 7px rgba(0, 0, 0, 0.05), -4px -4px 7px rgba(0, 0, 0, 0.05);
    h1 {
      color: $header-color-dark;
      font-size: 1.5em;
      letter-spacing: 0.15em;
      text-align: center;
      margin: 32px 0;
      font-family: 'Montserrat';
    }
    .formFooter {
      display: flex;
      margin: 20px auto 8px auto;
      a {
        margin: auto 0;
        color: black;
        font-size: 20px;
        font-family: 'Montserrat';
        text-decoration: none;
      }
    }
    .plane {
      height: 40px;
      width: auto;
      position: absolute;
      top: 20px;
      left: auto;
      bottom: auto;
      right: 20px;
    }
  }
}
</style>
