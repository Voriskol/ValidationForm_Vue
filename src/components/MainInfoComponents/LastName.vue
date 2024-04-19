<script>
import { required, minLength } from "vuelidate/lib/validators";

export default {
  data() {
    return {
      lastName: "",
    };
  },
  validations: {
    lastName: {
      required,
      minLength: minLength(2),
    },
  },

  methods: {
    setlastName(value) {
      this.lastName = value;
      this.$v.lastName.$touch();
    },
  },
};
</script>

<template>
  <form action="">
    <div
      class="form-group"
      :class="{ 'form-group--error': $v.lastName.$error }"
    >
      <label class="form__label">Фамилия*: </label>
      <input
        class="form__input"
        v-model.trim="lastName"
        @input="setlastName($event.target.value)"
      />
    </div>
    <div class="error" v-if="!$v.lastName.required">
      Поле обязательно для заполнения
    </div>
    <div class="error" v-if="!$v.lastName.minLength">
      Поле должно содержать хотя бы
      {{ $v.lastName.$params.minLength.min }} буквы.
    </div>
  </form>
</template>
