<script>
import { required, minLength } from "vuelidate/lib/validators";
export default {
  props: {
    firstName: String,
    lastName: String,
    patronymic: String,
    birthday: String,
    phoneNumber: String,
  },
    validations: {
      firstName: {
        required,
        minLength: minLength(2),
      },
      lastName: {
        required,
        minLength: minLength(2),
      },
      birthday: {
        required,
        minLength: minLength(10),
      },
      phoneNumber: {
        minLength: minLength(12),
      },
    },
    methods: {
    setfirstName(value) {
      this.firstName = value;
      this.$v.firstName.$touch();
    },
  },
};
</script>

<template></template>
