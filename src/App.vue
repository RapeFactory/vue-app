<template>
  <div id="app">
    <img src="./assets/logo.png">
    <hello-world v-bind:msg="greeting"/>
    <my-input v-bind:message="message"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import Input from './components/Input.vue';

export default {
  name: 'app',
  components: {
    'hello-world': HelloWorld,
    'my-input': Input,
  },
  data: function() {
    return {
      greeting: 'Vue.js App',
      message: 'Hi, input text here!'
    };
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
