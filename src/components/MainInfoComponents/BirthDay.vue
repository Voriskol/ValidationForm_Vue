<script>
import { required, minLength } from "vuelidate/lib/validators";

export default {
  data() {
    return {
      birthday: "",
    };
  },
  validations: {
    birthday: {
      required,
      minLength: minLength(10),
    },
  },

  methods: {
    setBirthday(value) {
      this.birthday = value;
      this.$v.birthday.$touch();
    },
  },
};
</script>

<template>
  <form action="">
    <div
      class="form-group"
      :class="{ 'form-group--error': $v.birthday.$error }"
    >
      <label class="form__label">Дата рождения*: </label>
      <input
        placeholder="дд.мм.гггг"
        class="form__input"
        v-model.trim="birthday"
        @input="setBirthday($event.target.value)"
      />
    </div>
    <div class="error" v-if="!$v.birthday.required">
      Поле обязательно для заполнения
    </div>
    <div class="error" v-if="!$v.birthday.minLength">
      Введите полную дату рождения
    </div>
  </form>
</template>
