<script>
export default {
  data() {
    return {
      picked: "",
    };
  },
};
</script>

<template>
  <div>
    <label class="form__label">Пол: {{ picked }} </label> <br />
    <input type="radio" id="first" value="Мужчина" v-model="picked" />
    <label for="first">Мужчина</label> <br />
    <input type="radio" id="second" value="Женщина" v-model="picked" />
    <label for="second">Женщина</label> <br />
  </div>
</template>
