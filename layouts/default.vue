<template>
  <div class="font-monserrat text-slate max-w-3xl mx-auto">
    <div v-show="!isLoading">
      <header-main />
      <Nuxt />
      <footer-main />
    </div>
    <loader-hamster v-show="isLoading" />
  </div>
</template>

<script>
import HeaderMain from '~/components/Header.vue'
import FooterMain from '~/components/Footer.vue'
import LoaderHamster from '~/components/LoaderHamster.vue'

export default {
  components: {
    HeaderMain,
    FooterMain,
    LoaderHamster,
  },
  data: () => ({
    isLoading: true,
  }),
  beforeCreate() {
    this.isLoading = true
  },
  mounted() {
    this.isLoading = false
  },
}
</script>
