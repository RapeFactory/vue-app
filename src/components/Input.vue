<template>
  <transition name="run">
    <div class="root" v-if="visible">
      <input class="input" :class="{colored: isColored}" @keyup.enter="onEnter" @input="onInput" v-model="value" type="text">
      <h1>{{ value }}</h1>
      <transition name="fade">
        <h1 v-if="isColored">{{ reversedValue }}</h1>
      </transition>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'my-input',
  props: {
    message: {
      type: String,
      required: true,
    },
    visible: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      isColored: false,
      value: this.message,
    };
  },
  computed: {
    reversedValue() {
      return this.value
        .split('')
        .reverse()
        .join('');
    },
  },
  methods: {
    onInput() {
      this.isColored = this.value.length >= 10;
    },
    onEnter() {
      this.$emit('message-saved', this.value);
    },
  },
};
</script>

<style lang="scss" scoped>
.root {
  position: relative;
  left: 0%;
}
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
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.run-enter {
  left: -60%;
}
.run-leave-to {
  left: 60%;
}
.run-leave-active,
.run-enter-active {
  transition: all 0.5s ease;
}
</style>
