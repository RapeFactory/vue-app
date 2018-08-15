<template>
  <div>
    <input class="input" :class="{colored: isColored}" @input="colorise" v-model="message" type="text">
  <h1>{{ message }}</h1>
  <h1>{{ reversedMessage }}</h1>
  </div>
</template>

<script>
export default {
  name: 'my-input',
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
      this.isColored = this.message.length >= 10;
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
