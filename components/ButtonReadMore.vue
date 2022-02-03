<template>
  <div>
    <button
      class="
        h-10
        bg-gray-50
        rounded-lg
        border-gray-200 border
        px-8
        hover:bg-purple-500 hover:text-white hover:border-2
      "
    >
      Continua leyendo
    </button>
  </div>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      default: '',
    },
  },
}
</script>
