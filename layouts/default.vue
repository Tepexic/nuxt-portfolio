<template>
  <div id="app" class="content-wrapper bg-background-primary font-sans text-copy-primary leading-normal0 min-h-screen flex flex-col" :class="theme">
    <Navigation :theme="theme" @themeChanged="updateTheme"/>
    <div class="flex-1">
      <transition name="moveUp" mode="out-in">
        <Nuxt :theme="theme"/>
      </transition>
    </div>
    <Foot/>
  </div>
</template>

<script>
import Navigation from '@/components/Navigation'
import Foot from '@/components/Foot'
export default {
  data: function () {
    return {
      theme: '',
    }
  },

  components: {
    Navigation,
    Foot
    },

  methods: {
    updateTheme(theme) {
      this.theme = theme
    }
  },

  mounted() {
    this.theme = localStorage.getItem('theme') || 'theme-light'
  },
}
</script>

<style>
  @import './../assets/css/tailwind.css';
  
  /*Transition animations*/
  .moveUp-enter-active {
    animation: fadeIn 1s ease-in;
  }
  @keyframes fadeIn {
    0%{
      opacity: 0;
    }
    50%{
      opacity: 0.5;
    }
    100%{
      opacity: 1;
    }
  }
  .moveUp-leave-active {
    animation: moveUp 0.3s ease-in;
  }
  @keyframes moveUp {
    0%{
      transform: translateY(0px);
    }
    100%{
      transform: translateY(-400px);
    }
  }
  .fade-enter-active, .fade-leave-active {
    transition: opacity 0.8s;
  }
  .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0;
  }
</style>
