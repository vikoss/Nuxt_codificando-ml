<template>
  <div class="mb-9">
    <figure>
      <img :src="blog.image" :alt="blog.title" />
    </figure>
    <subtitle class="my-1" :label="blog.title" />
    <paragraph :label="blog.description" />
    <nuxt-link :to="`/articulos/${blog.name}`">
      <button-read-more class="mt-3" text="Continua leyendo" />
    </nuxt-link>
  </div>
</template>

<script>
import Subtitle from '~/components/Typography/Subtitle.vue'
import Paragraph from '~/components/Typography/Paragraph.vue'
import ButtonReadMore from '~/components/ButtonReadMore.vue'

export default {
  components: {
    Subtitle,
    Paragraph,
    ButtonReadMore,
  },
  props: {
    blog: {
      type: Object,
      default: () => ({}),
    },
  },
}
</script>
