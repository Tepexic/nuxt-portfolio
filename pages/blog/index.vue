<template>
  <div class="mx-auto container px-4 md:container-inner  md:px-4  lg:px-40 lg:container-inner xl:container-inner">
    <div class="xl:flex xl:flex-wrap xl:justify-between">
      <Entry v-for="a in articles" :key="a.slug" :title="a.title" :description="a.description"
        :author="a.author.name" :date="a.createdAt" :link="a.slug" :tags="a.tags"
        :hero="a.img.includes('http') ? a.img : 'blog/' + a.img"/>
    </div>
  </div>
</template>

<script>
import Entry from '@/components/Entry'

export default {
  async asyncData({ $content, params }) {
    const articles = await $content('articles', params.slug)
      .only(['title', 'description', 'img', 'slug', 'author'])
      .sortBy('createdAt', 'desc')
      .fetch()
    return {
      articles
    }
  },
  
  components: { Entry },

}
</script>

<style scoped>
</style>