<template>
  <div class="alert alert-primary">
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <button class="btn btn-primary mb-3" v-on:click="doAction">
      Show/Hide
    </button>
    <transition name="transit">
      <p v-if="flg" class="trans">Transition!</p>
    </transition>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function () {
    return {
      title: "Trans&Anim",
      message: "Transition Sample!",
      flg: true,
      btn: "Hide",
    };
  },
  methods: {
    doAction() {
      this.flg = !this.flg;
    },
  },
};
</script>

<style>
.trans {
  background-color: black;
  color: white;
  padding: 10px;
  font-size: 20pt;
}
.transit-leave-active {
  animation: anim 3s;
}
.transit-enter-active {
  animation: anim 2.5s reverse;
}

@keyframes anim {
  0% {
    transform: translateX(0px) translateY(0px) rotateZ(0deg);
    opacity: 1;
    background-color: #ddf;
  }
  25% {
    transform: translateX(250px) translateY(0px) rotateZ(0deg);
    opacity: 1;
    background-color: #fdd;
  }
  50% {
    transform: translateX(0px) translateY(-100px) rotateZ(540deg);
    opacity: 1;
    background-color: #dfd;
  }
  75% {
    transform: translateX(250px) translateY(-100px) rotateZ(540deg);
    opacity: 1;
    background-color: #fdf;
  }
  100% {
    transform: translateX(0px) translateY(-200px) rotateZ(1080deg);
    opacity: 0;
    background-color: #ffd;
  }
}
</style>

