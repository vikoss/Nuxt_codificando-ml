<template>
  <div class="py-2">
    <h1
      class="
        line-1
        my-0
        mx-auto
        w-80
        border-r-2 border-solid border-slate
        whitespace-nowrap
        overflow-hidden
        typewriter
      "
    >
      ¿Quién es "Vikoss" 🤓️?
    </h1>
  </div>
</template>

<style scoped>
.typewriter {
  font-size: 26px;
  letter-spacing: 0.5px;
  animation: typewriter 2s steps(22) 500ms 1 normal both,
    blinkTextCursor 300ms steps(25), blinkTextCursor 1s infinite 2s;
}
@keyframes typewriter {
  from {
    width: 0;
  }
  to {
    width: 320px;
  }
}
@keyframes blinkTextCursor {
  from {
    border-right-color: #0f172a;
  }
  to {
    border-right-color: transparent;
  }
}
</style>
