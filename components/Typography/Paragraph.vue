<template>
  <div>
    <p class="text-gray-500 text-sm">{{ label }}</p>
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
