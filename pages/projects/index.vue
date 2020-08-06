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
          title: 'Whack-a-Vue',
          description: "Vue implementation of the Whack-A-Mole game, as seen in Wes Bos' Javascript30 course, with levels, all time high score and restarting countdown timer",
          link: 'https://tepexic.com/whack-a-vue/',
          ghlink: 'https://github.com/Tepexic/whack-a-vue',
          tecs: ['vue', 'tailwind', 'localStorage'],
          hero: 'https://tepexic.com/whack-a-vue/whack-a-vue.gif'
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