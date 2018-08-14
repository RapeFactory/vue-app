<template>
  <div>
  <input v-model="message" type="text">
  <h1 v-on="message">{{ message }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Input',
  data: function() {
    return {
      message: 'Вводи',
    };
  },
};
</script>

<style scoped>
input {
  width: 200px;
  height: 30px;
  font-size: 25px;
  text-align: center;
}
</style>
