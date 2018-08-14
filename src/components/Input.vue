<template>
  <div>
  <input v-model="message" type="text">
  <h1>{{ message }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Input',
  data: function() {
    return {
      message: 'message',
    };
  },
};
</script>

<style scoped>
input {
  width: 20%;
  height: 30px;
  font-size: 25px;
  text-align: center;
}
</style>
