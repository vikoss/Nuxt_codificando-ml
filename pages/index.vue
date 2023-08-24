<template>
  <main>
    <div class="bg-slate px-3 pt-8 pb-4">
      <typing-effect class="bg-white" />
    </div>
    <word-list-animation class="mt-8" />
    <div class="m-5 p-2" style="box-shadow: 0px 0px 16px #00000029">
      <h1 class="text-justify">
        Hola me llamo Víctor Israel y soy un artista expresandome a travez de
        lineas de codigo. Me encanta tener retos tecnicos y sobre todo compartir
        conocimientos para aprender mas y continuar creciendo en la industria
        Tech.
      </h1>
    </div>
    <div class="m-5">
      <h3 class="text-5xl mb-4">Artículos ✍🏻</h3>
      <view-article v-for="(blog, key) in blogs" :key="key" :blog="blog" />
    </div>
  </main>
</template>

<script>
import ViewArticle from '~/components/Article.vue'
import Blogs from '~/articles'
import TypingEffect from '~/components/TypingEffect.vue'
import WordListAnimation from '~/components/WordListAnimation.vue'

export default {
  components: {
    ViewArticle,
    TypingEffect,
    WordListAnimation,
  },
  computed: {
    blogs() {
      return Blogs
    },
  },
}
</script>
