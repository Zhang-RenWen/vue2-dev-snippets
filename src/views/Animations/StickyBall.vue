<template>
  <div>
    <div class="wrap">
      <div class="drop-outer">
        <svg class="drop" viewBox="0 0 40 40" version="1.1" xmlns="http://www.w3.org/2000/svg">
          <circle cx="20" cy="20" r="20" />
        </svg>
      </div>
      <div class="ripple ripple-1">
        <svg
          class="ripple-svg"
          viewBox="0 0 60 60"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
        >
          <circle cx="30" cy="30" r="24" />
        </svg>
      </div>
      <div class="ripple ripple-2">
        <svg
          class="ripple-svg"
          viewBox="0 0 60 60"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
        >
          <circle cx="30" cy="30" r="24" />
        </svg>
      </div>
      <div class="ripple ripple-3">
        <svg
          class="ripple-svg"
          viewBox="0 0 60 60"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
        >
          <circle cx="30" cy="30" r="24" />
        </svg>
      </div>
    </div>
    <div class="effect">
      <div class="blackball" />
      <div class="redball" />
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
.effect {
  width: 300px;
  height: 100%;
  padding-top: 50px;
  -webkit-filter: contrast(10);
  background: #fff;
}

.blackball {
  width: 100px;
  height: 100px;
  background: black;
  padding: 10px;
  border-radius: 50%;
  margin: 0 auto;
  z-index: 1;
  -webkit-filter: blur(5px);
}

.redball {
  width: 60px;
  height: 60px;
  background: #f00;
  padding: 10px;
  border-radius: 50%;
  position: absolute;
  top: 70px;
  left: 50px;
  z-index: 2;
  -webkit-filter: blur(5px);
  -webkit-animation: rball 6s infinite;
}

@-webkit-keyframes rball {
  0%,
  100% {
    left: 35px;
    width: 60px;
    height: 60px;
  }

  4%,
  54% {
    width: 60px;
    height: 60px;
  }

  10%,
  60% {
    width: 50px;
    height: 70px;
  }

  20%,
  70% {
    width: 60px;
    height: 60px;
  }

  34%,
  90% {
    width: 70px;
    height: 50px;
  }

  41% {
    width: 60px;
    height: 60px;
  }

  50% {
    left: calc(100% - 95px);
    width: 60px;
    height: 60px;
  }
}

.wrap {
  position: absolute;
  width: 100px;
  height: 200px;
  left: 50%;
  margin-left: -50px;
  top: 50%;
  margin-top: -100px;
}

.drop {
  width: 40px;
  height: 40px;
  left: 50%;
  margin-left: -20px;
  position: absolute;
  animation: drop 2s cubic-bezier(0.55, 0.085, 0.68, 0.53) 0s infinite;
}

.drop circle {
  fill: #2a96ed;
}

.drop-outer {
  position: absolute;
  /* border: 1px solid #333; */
  width: 100px;
  height: 200px;
  overflow: hidden;
  border-bottom-right-radius: 50px;
  border-bottom-left-radius: 50px;
  backface-visibility: hidden;
  transform: translate3d(0, 0, 0);
  background-clip: padding-box;
  -webkit-mask-image: -webkit-radial-gradient(circle, white 100%, black 100%);
}

.ripple {
  position: absolute;
  width: 240px;
  height: 240px;
  top: 68px;
  left: -70px;
  perspective: 100;
  transform: rotateX(65deg);
}

.ripple .ripple-svg {
  position: absolute;
  width: 240px;
  height: 240px;
  opacity: 0;
}

.ripple .ripple-svg circle {
  fill: none;
  stroke: #2a96ed;
  stroke-width: 10px;
  stroke-alignment: inner;
}

.ripple-1 {
  animation: ripple 2s cubic-bezier(0.25, 0.46, 0.45, 0.94) 0s infinite;
}

.ripple-1 .ripple-svg {
  animation: fade-in-out 2s linear 0s infinite;
}

.ripple-1 .ripple-svg circle {
  animation: border 2s cubic-bezier(0.25, 0.46, 0.45, 0.94) 0s infinite;
}

.ripple-2 {
  animation: ripple 2s cubic-bezier(0.25, 0.46, 0.45, 0.94) 0.2s infinite;
}

.ripple-2 .ripple-svg {
  animation: fade-in-out 2s linear 0.2s infinite;
}

.ripple-2 .ripple-svg circle {
  animation: border 2s cubic-bezier(0.25, 0.46, 0.45, 0.94) 0.2s infinite;
}

.ripple-3 {
  animation: ripple 2s cubic-bezier(0.25, 0.46, 0.45, 0.94) 0.35s infinite;
}

.ripple-3 .ripple-svg {
  animation: fade-in-out 2s linear 0.35s infinite;
}

.ripple-3 .ripple-svg circle {
  animation: border 2s cubic-bezier(0.25, 0.46, 0.45, 0.94) 0.35s infinite;
}

@keyframes drop {
  0% {
    transform: scale3d(0.01, 0.01, 0.01) translateY(0);
  }

  10% {
    transform: scale3d(1, 1, 1);
  }

  44% {
    transform: scale3d(1, 1, 1) translateY(200px);
  }

  100% {
    transform: scale3d(1, 1, 1) translateY(200px);
  }
}

@keyframes fade-in-out {
  0% {
    opacity: 0;
  }

  42% {
    opacity: 0;
  }

  52% {
    opacity: 1;
  }

  65% {
    opacity: 1;
  }

  100% {
    opacity: 0;
  }
}

@keyframes ripple {
  0% {
    transform: rotateX(65deg) scale3d(0.2, 0.2, 0.2);
  }

  42% {
    transform: rotateX(65deg) scale3d(0.2, 0.2, 0.2);
  }

  100% {
    transform: rotateX(65deg) scale3d(0.9, 0.9, 0.9);
  }
}

@keyframes border {
  0% {
    stroke-width: 6px;
  }

  42% {
    stroke-width: 6px;
  }

  100% {
    stroke-width: 2px;
  }
}
</style>
