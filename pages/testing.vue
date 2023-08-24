<template>
  <div>
    <word-list-animation />
    <br />
    <br />
    <typing-effect v-show="isMounted" />
  </div>
</template>

<script>
import TypingEffect from '~/components/TypingEffect.vue'
import WordListAnimation from '~/components/WordListAnimation.vue'

export default {
  components: {
    WordListAnimation,
    TypingEffect,
  },
  data() {
    return {
      isMounted: false,
    }
  },
  mounted() {
    this.isMounted = true
  },
}
</script>

<style></style>
