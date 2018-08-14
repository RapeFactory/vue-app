<template>
  <div class="hello">
    <h1 v-on:click="hover" >{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  methods: {
    hover: function() {
      this.msg += ' Makeev';
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  background: lemonchiffon;
  animation-name: anim;
  animation-duration: 5s;
  animation-iteration-count: infinite;
  animation-timing-function: ease;

  width: 20%;
  margin-right: 60%;
  margin-left: 40%;
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
