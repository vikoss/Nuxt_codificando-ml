<template>
  <header class="flex justify-between items-center bg-slate pt-2 px-2">
    <section>
      <nuxt-link class="flex justify-center items-center" to="/">
        <figure>
          <img
            class="h-16 w-auto"
            src="~/assets/logos/vikoss-transparent.png"
            alt="Logo"
          />
        </figure>
      </nuxt-link>
    </section>
    <section>
      <div class="menu-hamburger relative z-20">
        <button
          id="button-hamburger-animation"
          class="border-0 cursor-pointer p-0 w-14 h-14"
          @click="openMenu"
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
        <div
          v-show="classOpen"
          class="
            bg-slate
            text-white text-3xl
            absolute
            inset-0
            max-w-3xl
            mx-auto
            z-10
          "
        >
          <nav>
            <ul>
              <li><a href="home.html">Home</a></li>
              <li><a href="home.html">Articulos</a></li>
              <li><a href="home.html">Contacto</a></li>
              <li><a href="home.html">Acerca de mi</a></li>
            </ul>
          </nav>
        </div>
      </transition>
    </section>
  </header>
</template>

<script>
export default {
  data: () => ({
    classOpen: false,
  }),
  methods: {
    openMenu() {
      const button = document.getElementById('button-hamburger-animation')
      if (this.classOpen) {
        button.classList.toggle('close')
      } else {
        button.classList.toggle('open')
      }
      this.classOpen = !this.classOpen
    },
  },
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

.menu-hamburger button.close .top-line {
  animation-name: top-line-animation-close;
}

.menu-hamburger button.close .middle-line {
  animation-name: middle-line-animation-close;
}

.menu-hamburger button.close .bottom-line {
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
