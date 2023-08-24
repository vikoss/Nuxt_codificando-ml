<template>
  <div class="flex justify-center gap-5 text-3xl h-10 overflow-hidden">
    <div class="fade-out">
      <p class="text-pink font-bold">[</p>
    </div>
    <div>
      <ul class="change-text text-center">
        <li class="mb-1">Software Engineer</li>
        <li class="mb-1">Free Geek</li>
        <li class="mb-1">Evangelizador Vue</li>
        <li class="mb-1">Development lover</li>
      </ul>
    </div>
    <div class="fade-out">
      <p class="text-pink font-bold">]</p>
    </div>
  </div>
</template>

<style scoped>
.fade-out {
  animation-name: opacity;
  animation-duration: 1s;
  animation-iteration-count: infinite;
}

.change-text {
  animation-name: change;
  animation-duration: 10s;
  animation-iteration-count: infinite;
}

@keyframes opacity {
  0%,
  100% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
}

@keyframes change {
  0%,
  12.66%,
  100% {
    transform: translate3d(0, 0, 0);
  }
  16.66%,
  29.32% {
    transform: translate3d(0, -25%, 0);
  }
  33.32%,
  45.98% {
    transform: translate3d(0, -50%, 0);
  }
  49.98%,
  62.64% {
    transform: translate3d(0, -75%, 0);
  }
  66.64%,
  79.3% {
    transform: translate3d(0, -50%, 0);
  }
  83.3%,
  95.96% {
    transform: translate3d(0, -25%, 0);
  }
}

/*
// 6 is the number of animation.
// Here, there are 4 lines :

// 1 to 2
// 2 to 3
// 3 to 4
// 4 to 3
// 3 to 2
// 2 to 1

// 6x + 6y = 100 (100% duration)

// HERE :
// y = 4 -> Animation between two lines
// x = 12.66 -> Time spent on a line

// You can define a value and calculate the other if you want change speed or the number of lines
 */
</style>
