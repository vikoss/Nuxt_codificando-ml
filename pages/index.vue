<template>
  <main class="">
    <div class="bg-gray-900 px-5 py-3 h-32">
      <div
        :class="{ 'css-typing': typeEffectClass, hidden: !typeEffectClass }"
        class="text-gray-500 bg-white p-3"
      >
        <h1>
          Hola
          <strong class="text-2xl">👋🏻️</strong>
          mi nombre es Víctor Israel
        </h1>
        <h1>
          y soy desarrollador full stack
          <strong class="text-2xl">🤓️</strong>
        </h1>
      </div>
    </div>
    <div class="m-5 p-2 shadow-md text-gray-500">
      <h2 class="text-justify">
        "Codificando" es un blog dedicado a compartir con todo el mundo pero en
        especial a la comunidad Geek informacion acerca de tecnolgia enfocado en
        Laravel y Vue Js.
      </h2>
    </div>
    <div class="m-5">
      <h2 class="text-5xl mb-4">Artículos ✍️</h2>
      <view-article v-for="(blog, key) in blogs" :key="key" :blog="blog" />
    </div>
  </main>
</template>

<script>
import ViewArticle from '~/components/Article.vue'
import Blogs from '~/blogs'

export default {
  components: {
    ViewArticle,
  },
  data: () => ({
    typeEffectClass: false,
  }),
  computed: {
    blogs() {
      return Blogs
    },
  },
  mounted() {
    this.typeEffectClass = true
  },
}
</script>

<style scoped>
.css-typing h1 {
  border-right: 0.15em solid #111827;
  font-size: 20px;
  white-space: nowrap;
  overflow: hidden;
  font-weight: 500;
}
.css-typing h1:nth-child(1) {
  width: 15.5em;
  animation: type 1.5s steps(40, end);
  animation-fill-mode: forwards;
}

.css-typing h1:nth-child(8) {
  width: 7em;
  opacity: 0;
  animation: type2 1.8s steps(40, end);
  animation-delay: 0.5s;
  animation-fill-mode: forwards;
}

.css-typing h1:nth-child(2) {
  width: 13.7em;
  opacity: 0;
  animation: type3 1.5s steps(60, end), blink 0.5s step-end infinite alternate;
  animation-delay: 1.5s;
  animation-fill-mode: forwards;
}

@keyframes type {
  0% {
    width: 0;
  }
  99.9% {
    border-right: 0.15em solid #111827;
  }
  100% {
    border: none;
  }
}

@keyframes type2 {
  0% {
    width: 0;
  }
  1% {
    opacity: 1;
  }
  99.9% {
    border-right: 0.15em solid #111827;
  }
  100% {
    opacity: 1;
    border: none;
  }
}

@keyframes type3 {
  0% {
    width: 0;
  }
  1% {
    opacity: 1;
  }
  100% {
    opacity: 1;
  }
}

@keyframes blink {
  50% {
    border-color: transparent;
  }
}
</style>
