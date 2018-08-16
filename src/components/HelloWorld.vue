<template>
  <div class="hello">
    <h1 @click="click" >{{ greeting }}</h1>
  </div>
</template>

<script>
export default {
  name: 'hello-world',
  props: {
    greeting: {
      type: String,
      required: true,
    },
  },
  methods: {
    click() {
      this.$emit('click');
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  background: lemonchiffon;
  animation-name: anim;
  animation-duration: 10s;
  animation-iteration-count: infinite;
  animation-timing-function: ease;

  width: 20%;
  margin-right: 60%;
  margin-left: 40%;
  border-radius: 10px;
}

@keyframes anim {
  0% {
    background: lemonchiffon;
    margin-right: 60%;
    margin-left: 40%;
  }
  25% {
    background: yellowgreen;
    margin-right: 0%;
    margin-left: 80%;
  }
  50% {
    background: teal;
    margin-right: 60%;
    margin-left: 40%;
  }
  75% {
    background: yellowgreen;
    margin-right: 100%;
    margin-left: 0%;
  }
  100% {
    background: lemonchiffon;
    margin-right: 60%;
    margin-left: 40%;
  }
}
</style>
