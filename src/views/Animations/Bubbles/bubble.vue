<template>
  <div class="frame">
    <div class="bubble animation-bubble-move">
      <div class="refraction-top" />
      <div class="refraction-bottom" />
      <div class="light animation-light-move" />
      <div class="cover" />
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  props: {},
  data() {
    return {}
  },

  mounted() {},
  methods: {}
}
</script>

<style lang="scss" scoped>
.frame {
  display: flex;
  flex-wrap: wrap;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-25%, -50%);
  width: 400px;
  height: 400px;
  background-color: #000;
  border: 6px solid rgb(73, 73, 73);
  border-radius: 6px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 1);
  overflow: hidden;
}

.bubble {
  width: 50%;
  height: 50%;
  border-radius: 50%;
  background-color: #000;
  transform: translate(50%, 50%);
}

.refraction-top {
  width: 90%;
  height: 90%;
  border-radius: 50%;
  position: absolute;
  left: 5%;
  top: 1%;
  background-image: radial-gradient(
    circle at 50% 60%,
    rgba(0, 0, 0, 0) 0%,
    rgba(0, 0, 0, 0) 60%,
    rgba(64, 0, 0, 0.401) 65%,
    #ff00ff81 80%,
    #ffea00a9 90%,
    #ffea00 100%
  );
}
.refraction-bottom {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  position: absolute;
  background-image: radial-gradient(
    circle at 50% 43%,
    rgba(0, 0, 0, 0) 0%,
    rgba(0, 0, 0, 0) 50%,
    rgba(64, 0, 255, 0.401) 60%,
    #ff00ff81 65%,
    #ffea0090 70%,
    #ffea00 100%
  );
}

.light {
  background: #ffffff;
  width: 7%;
  height: 25%;
  position: absolute;
  left: 10%;
  top: 15%;
  transform: rotate(30deg);
  filter: blur(3px);
  border-radius: 50% / 50%;
}

.cover {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #000;
  animation: broken 0.5s cubic-bezier(0.72, 0.37, 1, 1) 0.4s normal both;
}

.animation-light-move {
  animation: light-move 1s cubic-bezier(0.72, 0.37, 1, 1) 0s infinite both;
}

.animation-bubble-move {
  animation: bubble-move 1s cubic-bezier(0.73, 0.39, 1, 0.5) 0s normal both;
}

@keyframes broken {
  0% {
    transform: translate(-35%, -35%) scale(0);
  }
  57% {
    transform: translate(-35%, -35%) scale(0);
  }
  65% {
    transform: translate(-1%, -1%) scale(1.05);
  }
  100% {
    transform: translate(-1%, -1%) scale(1.05);
  }
}

@keyframes light-move {
  0% {
    transform: translate(0%, 0%) rotate(30deg);
  }
  25% {
    transform: translate(10%, 10%) rotate(28deg);
  }
  45% {
    transform: translate(5%, 5%) rotate(30deg);
  }
  50% {
    transform: translate(12%, 0%) rotate(30deg);
  }
  60% {
    transform: translate(-100%, 10%) rotate(30deg) scale(0);
  }
  100% {
    transform: translate(-100%, 20%) rotate(30deg) scale(0);
  }
}

@keyframes bubble-move {
  0% {
    transform: translate(50%, 50%);
  }

  25% {
    transform: translate(52%, 52%);
  }
  45% {
    transform: translate(48%, 48%);
  }
  50% {
    transform: translate(40%, 45%);
  }
  60% {
    transform: translate(50%, 40%);
  }
  65% {
    transform: translate(65%, 35%);
  }
  70% {
    transform: translate(70%, 30%);
  }
  80% {
    transform: translate(80%, 25%);
  }
  90% {
    transform: translate(90%, 10%);
  }
  95% {
    transform: translate(95%, 5%);
  }
  100% {
    transform: translate(100%, 5%);
  }
}
</style>
