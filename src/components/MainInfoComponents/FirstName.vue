<script>
import { required, minLength } from "vuelidate/lib/validators";

export default {
  props: {
    title: String,
  },
  data() {
    return {
      firstName: "",
    };
  },
  validations: {
    firstName: {
      required,
      minLength: minLength(2),
    },
  },

  methods: {
    settitle(value) {
      this.firstName = value;
      this.$v.firstName.$touch();
    },
  },
};
</script>

<template>
  <form action="">
    <div
      class="form-group"
      :class="{ 'form-group--error': $v.firstName.$error }"
    >
      <label class="form__label">Имя*: </label>
      <input
        class="form__input"
        v-model.trim="firstName"
        @input="setfirstName($event.target.value)"
      />
    </div>
    <div class="error" v-if="!$v.firstName.required">
      Поле обязательно для заполнения
    </div>
    <div class="error" v-if="!$v.firstName.minLength">
      Поле должно содержать хотя бы
      {{ $v.firstName.$params.minLength.min }} буквы.
    </div>
  </form>
</template>
