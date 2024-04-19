<script>
export default {
  props: {
    title: String,
    option1: String,
    option2: String,
    option3: String,
  },
  data() {
    return {
      selected: this.option1,
    };
  },
};
</script>

<template>
  <div>
    <label class="form__label">{{ title }}: </label>
    <select v-model="selected">
      <option disabled value="">Выберите один из вариантов</option>
      <option>{{ option1 }}</option>
      <option>{{ option2 }}</option>
      <option>{{ option3 }}</option>
    </select>
  </div>
</template>
