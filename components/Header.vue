<template>
  <header class="flex justify-between items-center bg-gray-900 pt-2 px-2">
    <section class="">
      <nuxt-link class="flex justify-center items-center" to="/">
        <figure>
          <img
            class="h-10 w-auto bg-white"
            src="~/assets/terminal_x128.png"
            alt="Logo del blog CODIFICANDO"
          />
        </figure>
        <p
          class="text-white font-semibold text-lg"
          style="font-family: Comic Sans MS, Comic Sans, cursive"
        >
          Codificando
        </p>
      </nuxt-link>
    </section>
    <section class="">
      <div class="menu-hamburger">
        <button
          class="border-0 cursor-pointer p-0 w-14 h-14"
          :class="{ open: classOpen }"
          @click="classOpen = !classOpen"
        >
          <span
            class="top-line rounded bg-white block w-3/5 my-1.5 mx-auto h-0.5"
          >
          </span>
          <span
            class="
              middle-line
              rounded
              bg-white
              block
              w-3/5
              my-1.5
              mx-auto
              h-0.5
            "
          >
          </span>
          <span
            class="
              bottom-line
              rounded
              bg-white
              block
              w-3/5
              my-1.5
              mx-auto
              h-0.5
            "
          >
          </span>
        </button>
      </div>
      <transition name="fade">
        <nav
          v-show="classOpen"
          class="absolute right-0 p-2 bg-gray-600 text-white sm:hidden"
        >
          <ul>
            <li><a href="home.html">Home</a></li>
            <li><a href="home.html">Articulos</a></li>
            <li><a href="home.html">Contacto</a></li>
            <li><a href="home.html">Acerca de mi</a></li>
          </ul>
        </nav>
      </transition>
    </section>
  </header>
</template>

<script>
export default {
  data: () => ({
    classOpen: false,
  }),
}
</script>

<style>
.hamburgerR {
  display: block;
}

.menu-hamburger button span {
  animation-duration: 1s;
  animation-fill-mode: forwards;
}

.menu-hamburger button.open .top-line {
  animation-name: top-line-animation;
}

.menu-hamburger button.open .middle-line {
  animation-name: middle-line-animation;
}

.menu-hamburger button.open .bottom-line {
  animation-name: bottom-line-animation;
}

.menu-hamburger button .top-line {
  animation-name: top-line-animation-close;
}

.menu-hamburger button .middle-line {
  animation-name: middle-line-animation-close;
}

.menu-hamburger button .bottom-line {
  animation-name: bottom-line-animation-close;
}

@keyframes top-line-animation {
  50%,
  100% {
    margin: 0 auto;
    transform: translateY(2px) rotate(-45deg);
  }
}

@keyframes bottom-line-animation {
  50%,
  100% {
    margin: 0 auto;
    transform: translateY(-2px) rotate(45deg);
  }
}

@keyframes middle-line-animation {
  20%,
  100% {
    margin: 0 auto;
    width: 0;
    opacity: 0;
  }
}

@keyframes top-line-animation-close {
  0% {
    margin: 0 auto;
    transform: translateY(2px) rotate(-45deg);
  }

  50%,
  100% {
    margin: 6px auto;
    transform: translateY(0px) rotate(0deg);
  }
}

@keyframes bottom-line-animation-close {
  0% {
    margin: 0 auto;
    transform: translateY(-2px) rotate(45deg);
  }

  50%,
  100% {
    margin: 6px auto;
    transform: translateY(0px) rotate(0deg);
  }
}

@keyframes middle-line-animation-close {
  0% {
    margin: 0 auto;
    width: 0;
    opacity: 0;
  }

  20%,
  100% {
    margin: 6px auto;
    width: 60%;
    opacity: 1;
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.7s;
}
.fade-enter,
.fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
