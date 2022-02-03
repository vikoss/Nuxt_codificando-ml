<template>
  <div class="font-serif">
    <header-main />
    <Nuxt />
    <footer-main />
  </div>
</template>

<script>
import HeaderMain from '~/components/Header.vue'
import FooterMain from '~/components/Footer.vue'

export default {
  components: {
    HeaderMain,
    FooterMain,
  },
}
</script>
