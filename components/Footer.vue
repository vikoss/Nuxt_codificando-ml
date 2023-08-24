<template>
  <footer class="bg-gray-900 text-white h-14 flex items-center justify-center">
    <i>Copyright ©{{ year }} All rights reserved</i>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  data: () => ({
    year: new Date().getFullYear(),
  }),
}
</script>
