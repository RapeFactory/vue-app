<template>
  <div>
  <input v-model="message" type="text">
  <div v-on="message">{{ message }}</div>
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

<style>
</style>
