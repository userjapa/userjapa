<template>
  <div class="h-screen w-screen flex flex-col relative">
    <header class="text-center px-5 pt-5 md:text-base lg:text-lg xl:text-xl">
      <nav>
        <router-link to="/" class="mr-3">
          Main
        </router-link>
        <router-link to="/lightning-distance" class="mr-3">
          Lightning Distance
        </router-link>
        <router-link to="/face-recognition">
          Face Recognition
        </router-link>
      </nav>
    </header>
    <router-view class="flex-1 px-5"/>
    <footer class="p-5">
      <div class="flex justify-end items-center">
        <div class="footer-icon mr-2">
          <a href="https://github.com/userjapa" target="_blank"><fa-icon :icon="['fab', 'github']" /></a>
        </div>
          <div class="footer-icon mr-2 linkedin">
            <a href="https://www.linkedin.com/in/willian-hiroshi-simabukuro-06001a100" target="_blank"><fa-icon :icon="['fab', 'linkedin']" /></a>
          </div>
          <div class="footer-icon mr-2 telegram">
            <a href="https://t.me/userjapa" target="_blank"><fa-icon :icon="['fab', 'telegram']" /></a>
          </div>
        <div class="footer-icon mr-2">
          <a href="mailto:willian.hsimabukuro@gmail.com?subject=Contact"><fa-icon :icon="['far', 'envelope']" /></a>
        </div>
        <span>user<strong>Japa</strong></span>
      </div>
    </footer>
    <transition name="fade">
      <div class="black-lives-matter absolute w-full h-full flex justify-center items-center flex-col" v-show="firstAccess">
        <h1 class="text-4xl md:text-6xl"><strong>#BlackLivesMatter</strong></h1>
        <button class="my-5 px-5 py-3 rounded-sm" @click="firstAccess = false"><strong>I don't sympathize with fascists</strong></button>
      </div>
    </transition>
  </div>
</template>

<script type="text/javascript">
export default {
  data () {
    return {
      firstAccess: true
    }
  }
}
</script>

<style lang="scss">
.footer-icon {
  font-size: 2rem;
  &.telegram {
    color: #0088CC;
  }
  &.linkedin {
    color: #0E76A8;
  }
}

.black-lives-matter {
  background-color: rgba(black, .95);
  color: #444;

  button {
    background-color: #555;
    color: black;
    transition: background-color .2s, color .2s;
    outline: none;
    &:focus {
      outline: none;
    }
    &:hover {
      color: #222;
      background-color: #777;
    }
  }
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active em versões anteriores a 2.1.8 */ {
  opacity: 0;
}
</style>
