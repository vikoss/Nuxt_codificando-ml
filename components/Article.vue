<template>
  <div class="mb-9">
    <figure>
      <img :src="blog.image" :alt="blog.title" />
    </figure>
    <h2 class="text-2xl">{{ blog.title }}</h2>
    <p class="text-gray-500 text-sm">{{ blog.description }}</p>
    <nuxt-link :to="`/articulos/${blog.slug}`">
      <button-base class="mt-3" label="Continuar leyendo" />
    </nuxt-link>
  </div>
</template>

<script>
import ButtonBase from '~/components/ButtonBase.vue'

export default {
  components: {
    ButtonBase,
  },
  props: {
    blog: {
      type: Object,
      default: () => ({}),
    },
  },
}
</script>
