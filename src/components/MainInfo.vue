<script setup>
import FirstName from "./MainInfoComponents/FirstName.vue";
import LastName from "./MainInfoComponents/LastName.vue";
import BirthDay from "./MainInfoComponents/BirthDay.vue";
import PhoneNumber from "./MainInfoComponents/PhoneNumber.vue";
import TheSex from "./MainInfoComponents/TheSex.vue";
import InputList from "./MainInfoComponents/InputList.vue";
</script>

<template>
  <section class="MainInfo">
    <div class="container">
      <div class="auth_banner left">
        <h2>Основная информация</h2>
      </div>
      <div class="auth_form">
        <form action="">
          <FirstName />
          <LastName />
          <div>
            <label class="form__label">Отчество: </label>
            <input class="form__input" type="text" />
          </div>
          <BirthDay />
          <PhoneNumber />
          <TheSex />
          <InputList
            title="Группа клиентов*"
            option1="VIP"
            option2="Проблемные"
            option3="Стандарт"
          />
          <InputList
            title="Лечащий врач"
            option1="Иванов"
            option2="Захаров"
            option3="Чернышева"
          />
          <div>
            <label class="form__label">Не отправлять СМС: </label>
            <input type="checkbox" />
          </div>
        </form>
      </div>
    </div>
  </section>
</template>

<style lang="sass">
.MainInfo
  display: flex

.left
  color: #2271dd

.auth_form
</style>
