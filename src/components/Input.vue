<template>
  <div>
  <input class="input" v-bind:class="{colored: isColored}" v-model="message" @input="colorise" type="text">
  <h1>{{ message }}</h1>
  <h1>{{ reversedMessage }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Input',
  data: function() {
    return {
      message: 'message',
      isColored: false,
    };
  },
  computed: {
    // геттер вычисляемого значения
    reversedMessage: function() {
      // `this` указывает на экземпляр vm
      return this.message
        .split('')
        .reverse()
        .join('');
    },
  },
  methods: {
    colorise: function() {
      if (this.message.length > 10) {
        this.isColored = true;
      } else {
        this.isColored = false;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.input {
  width: 20%;
  height: 30px;
  font-size: 25px;
  text-align: center;
  border-top: none;
  border-left: none;
  border-right: none;
}
.colored {
  background-color: lemonchiffon;
}
</style>
