<script setup>
import MainInfo from "./components/MainInfo.vue";
import TheAddress from "./components/TheAddress.vue";
import ThePassport from "./components/ThePassport.vue";
</script>

<template>
  <div class="main">
    <div class="page__content">
      <div class="content__left">
        <h1 class="title">Регистрация</h1>
        <main-info />
      </div>
      <div class="content__right">
        <the-address />
        <the-passport />
        <div>
          <button>Отправить</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="sass">
@import "./styles/AppStyles.sass"
</style>
