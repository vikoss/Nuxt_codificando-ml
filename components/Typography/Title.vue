<template>
  <transition>
    <h1 class="text-3xl">{{ label }}</h1>
  </transition>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: '',
    },
  },
}
</script>
