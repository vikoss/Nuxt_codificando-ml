<template>
  <div>
    <button
      class="
        h-11
        bg-pink
        text-slate-light
        font-medium
        text-lg
        rounded-lg
        border-pink border
        px-8
      "
    >
      {{ label }}
    </button>
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
