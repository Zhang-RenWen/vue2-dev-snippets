<template>
  <!-- https://codepen.io/rishikumarr/pen/YzZZzmw -->
  <div class="flex body">
    <div class="book flex">
      <img :src="src" class="front" />
      <!--  <img src="https://raw.githubusercontent.com/rishikumarr/images/main/36.jpeg" class="front" /> -->
      <ul class="pages">
        <li class="page one" />
        <li class="page two" />
        <li class="page three" />
        <li class="page four" />
        <li class="page five" />
        <li class="page six" />
        <li class="page seven" />
      </ul>
      <div class="back" />
    </div>
  </div>
</template>

<script>
import img from '@/assets/image/bld.jpg'
export default {
  components: {},
  props: {},
  data() {
    return {
      // RAPTURE : The Strawberry Moon is the sixth of this year’s 12 named Full Moon phases (Pic: Getty) (Image: Getty)
      src: img
    }
  },

  mounted() {
    const book = document.querySelector('.book')
    book.addEventListener('click', function() {
      book.classList.toggle('open')
    })
  },

  methods: {}
}
</script>

<style lang="scss" scoped>
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
}

$paper: #e0e0e0;
$testing: 2px solid black;
$borderRad: 0.5em;
$shadowOpacity: rgba(0, 0, 0, 0.3);
$transition: 0.5s ease;

html {
  font-size: 62.5%;
}

.flex {
  display: flex;
  align-items: center;
  justify-content: center;
}

li {
  list-style-type: none;
}

.body {
  width: 100%;
  height: 80%;
  perspective: 200px;
  transform-style: preserve-3d;
}

.book {
  width: 2vw;
  max-width: 20em;
  min-width: 15em;
  height: 25em;
  border-radius: $borderRad;
  position: relative;
  box-shadow: 5px 20px 20px $shadowOpacity;
  z-index: 8;
  cursor: pointer;
}

.book.open {
  box-shadow: 5px 20px 20px $shadowOpacity;
  animation: open 0.6s ease forwards;
}

.front {
  width: 100%;
  height: 100%;
  z-index: 3;
  border-radius: inherit;
  z-index: 7;
  transition: $transition;
  box-shadow: 5px 10px 20px $shadowOpacity;
}

.back {
  transition: 0.5s ease;
  opacity: 0;
  transform: translateX(0%);
}

.open .back {
  width: 100%;
  height: 92%;
  position: absolute;
  top: 4%;
  left: 0%;
  background-image: url(https://raw.githubusercontent.com/rishikumarr/images/main/36.jpeg);
  z-index: 1;
  border-radius: inherit;
  box-shadow: 5px 10px 20px $shadowOpacity;
  animation: slideIn2 0.5s ease forwards;
}

li {
  top: 50%;
  left: 0%;
  transition: $transition;
  transform: translateY(-50%) translateX(0%);
  opacity: 0;
  /* border : $testing) */
}

.open li {
  position: absolute;
  border-right: 1px solid rgba(255, 255, 255, 0.4);
  border-radius: 0.5em;
  /* border : $testing); */
  animation: slideIn1 0.5s ease 0.1s forwards;
}

.one,
.two,
.three,
.four,
.five,
.six,
.seven {
  transition: $transition;
}

.open .one {
  z-index: 6;
  width: 92%;
  height: 97%;
  background-color: rgba(224, 224, 224, 0.9);
}

.open .two {
  z-index: 5;
  width: 93%;
  height: 96%;
  background-color: rgba(224, 224, 224, 0.85);
}

.open .three {
  z-index: 4;
  width: 94%;
  height: 95%;
  background-color: rgba(224, 224, 224, 0.75);
}

.open .four {
  z-index: 3;
  width: 95%;
  height: 94%;
  background-color: rgba(224, 224, 224, 0.65);
}

.open .five {
  z-index: 2;
  width: 96%;
  height: 93%;
  background-color: rgba(224, 224, 224, 0.6);
}

.open .six {
  z-index: 2;
  width: 97%;
  height: 92%;
  background-color: rgba(224, 224, 224, 0.6);
}

.open .seven {
  z-index: 2;
  width: 98%;
  height: 91%;
  background-color: rgba(224, 224, 224, 0.65);
}

@keyframes open {
  to {
    transform: translateX(-10%) rotateY(-10deg) translateZ(8px);
  }
}

@keyframes slideIn1 {
  0% {
    opacity: 0;
    transform: translateY(-50%) translateX(0%);
  }
  100% {
    opacity: 1;
    transform: translateY(-50%) translateX(10%);
  }
}

@keyframes slideIn2 {
  0% {
    opacity: 0;
    transform: translateX(0%);
  }
  100% {
    opacity: 1;
    transform: translateX(10%);
  }
}

@media only screen and (max-width: 800px) {
  .book {
    height: 28em;
  }
}
</style>
