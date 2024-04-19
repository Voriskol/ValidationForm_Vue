<script>
export default {
  data() {
    return {
      selected: "ОМС",
    };
  },
};
</script>

<template>
  <div>
    <label class="form__label">Группа клиентов*: </label>
    <select v-model="selected">
      <option disabled value="">Выберите один из вариантов</option>
      <option>VIP</option>
      <option>Проблемные</option>
      <option>ОМС</option>
    </select>
  </div>
</template>
