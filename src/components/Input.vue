<template>
  <div>
    <input class="input" :class="{colored: isColored}" @input="colorise" v-model="value" type="text">
    <h1>{{ value }}</h1>
    <h1>{{ reversedValue }}</h1>
  </div>
</template>

<script>
export default {
  name: 'my-input',
  props: {
    message: {
      type: String,
      required: true,
    },
  },
  data: function() {
    return {
      isColored: false,
      value: this.message,
    };
  },
  computed: {
    reversedValue: function() {
      return this.value
        .split('')
        .reverse()
        .join('');
    },
  },
  methods: {
    colorise: function() {
      this.isColored = this.value.length >= 10;
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
