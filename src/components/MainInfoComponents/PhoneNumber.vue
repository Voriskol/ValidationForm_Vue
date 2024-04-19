<script>
import { minLength } from "vuelidate/lib/validators";

export default {
  data() {
    return {
      phoneNumber: "",
    };
  },
  validations: {
    phoneNumber: {
      minLength: minLength(12),
    },
  },

  methods: {
    setphoneNumber(value) {
      this.phoneNumber = value;
      this.$v.phoneNumber.$touch();
    },
  },
};
</script>

<template>
  <form action="">
    <div
      class="form-group"
      :class="{ 'form-group--error': $v.phoneNumber.$error }"
    >
      <label class="form__label">Номер телефона: </label>
      <input
        placeholder="+70000000000"
        class="form__input"
        v-model.trim="phoneNumber"
        @input="setphoneNumber($event.target.value)"
      />
    </div>
    <div class="error" v-if="!$v.phoneNumber.minLength">
      Поле должно содержать 11 цифр
    </div>
  </form>
</template>
