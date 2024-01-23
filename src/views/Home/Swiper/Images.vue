<template>
  <div class="imgs">
    <ul>
      <li class="item" v-for="(image, index) in imageList" :key="index" :style="{
        'background-image': 'url(' + image + ')'
      }">
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">

// 需要替换这个列表
const imageList = [
  "https://file.xn--8mrz94a38l8mb00n.top/config/a3aab33f1f0cb0f3582d097c30b50ed3.jpeg",
  "https://file.xn--8mrz94a38l8mb00n.top/config/130479e9b9d41c3a9b12a6034eb369d6.jpeg",
  "https://file.xn--8mrz94a38l8mb00n.top/config/c3687c26f1f6763a0d9854bc7deb894e.jpeg",
  "https://file.xn--8mrz94a38l8mb00n.top/config/40b889ae65995a4429027dcf72cfd343.jpg",
  "https://file.xn--8mrz94a38l8mb00n.top/config/c5affe4729ad30725c7506629f6e2872.jpg",
  "https://file.xn--8mrz94a38l8mb00n.top/config/1dd74403eac332529608bc383515a486.jpg"
]
</script>

<style lang="scss" scoped>
@import "@/assets/styles/mixin.scss";

.imgs {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  z-index: -9;
  background-color: #363636;
  overflow: hidden;

  .item {
    @include absolute;
    width: 100%;
    height: 100%;
    background: no-repeat 50% 50% / cover;
    opacity: 0;
    animation: imageAnimation 36s linear infinite 0s;
    backface-visibility: hidden;
    transform-style: preserve-3d;

    &:nth-child(2) {
      animation-delay: 6s;
    }

    &:nth-child(3) {
      animation-delay: 12s;
    }

    &:nth-child(4) {
      animation-delay: 18s;
    }

    &:nth-child(5) {
      animation-delay: 24s;
    }

    &:nth-child(6) {
      animation-delay: 30s;
    }
  }

  &::before {
    content: '';
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .2);
    transition: all .2s ease-in-out 0s;
  }
}

@keyframes imageAnimation {
  0% {
    opacity: 0;
    animation-timing-function: ease-in;
  }

  2% {
    opacity: 1;
  }

  8% {
    opacity: 1;
    transform: scale(1.05);
    animation-timing-function: ease-out;
  }

  17% {
    opacity: 1;
    transform: scale(1.1);
  }

  25% {
    opacity: 0;
    transform: scale(1.1);
  }

  100% {
    opacity: 0;
  }
}
</style>