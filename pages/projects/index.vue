<template>
  <div class="mx-auto container px-4 md:container-inner  md:px-4  lg:px-40 lg:container-inner xl:container-inner">
    <Project v-for="p in projects" :key="p.title" :title="p.title" :description="p.description"
      :link="p.link" :ghlink="p.ghlink" :tecs="p.tecs" :hero="p.hero"/>
  </div>
</template>

<script>
import Project from '@/components/Project'
export default {

  data: function () {
    return {
      projects: [
        {
          title: 'Tip Calculator PWA',
          description: "A Progressive Web App of a simple tip calculator made in Vue, with range sliders for tip % and number of people to split the check with.",
          link: 'https://propina.netlify.app/',
          ghlink: 'https://github.com/Tepexic/tip-calculator-vue-pwa',
          tecs: ['vue', 'tailwind', 'localStorage', 'PWA'],
          hero: '/images/tip-pwa.png'
        },
        {
          title: 'LaTex Thesis Template',
          description: "An open-source LaTeX template for my university, forked from Cambridge's template. It has now been expanded to two extra universities. The repository averages 20 visitors/day in the last month",
          link: 'https://github.com/Tepexic/Tesis-UNAM/blob/master/tesis.pdf',
          ghlink: 'https://github.com/Tepexic/Tesis-UNAM',
          tecs: ['OSS', 'LaTeX'],
          hero: '/images/thesis.png'
        },
        {
          title: 'Whack-a-Vue',
          description: "Vue implementation of the Whack-A-Mole game, as seen in Wes Bos' Javascript30 course, with levels, all time high score and restarting countdown timer",
          link: 'https://whack-a-vue.netlify.app/',
          ghlink: 'https://github.com/Tepexic/whack-a-vue',
          tecs: ['vue', 'tailwind', 'localStorage'],
          hero: '/images/whack-a-vue.gif'
        },
        {
          title: '$ Vue',
          description: "$ Vue is an application to expenses and deposits across multiple cards, final project of Scrimba's Vue Bootcamp. Uses Vuex for state management and Vue Router for internal routing",
          link: 'https://tepexic.com/dollar-vue/',
          ghlink: 'https://github.com/Tepexic/dollar-vue',
          tecs: ['vue', 'vuex', 'vue router', 'tailwind'],
          hero: '/images/dollar-vue.png'
        }
      ]
    }
  },

  components: {
    Project
  }
}
</script>

<style>

</style>