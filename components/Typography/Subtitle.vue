<template>
  <div>
    <h2 class="text-2xl">{{ label }}</h2>
  </div>
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
