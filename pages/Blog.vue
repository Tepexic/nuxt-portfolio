<template>
  <div class="mx-auto container px-4 md:container-inner lg:container-inner xl:container-inner">
    <div class="flex-wrap items-center justify-center w-full">
      <Entry v-for="e in entries" :key="e.id"
        :title="e.title" :author="e.author"
        :date="e.date" :description="e.description"
        :hero="e.hero"
        :link="e.id" :tags="e.tags"/>
    </div>
  </div>
</template>

<script>
import posts from './../static/posts.json'
import Entry from './../components/Entry'

const blogEntries = []
Object.keys(posts).map(section => {
  posts[section].forEach(entry => {blogEntries.push(entry)})
})

export default {
  name: 'BlogIndex',

  data: function () {
    return {
      entries: blogEntries
    }
  },

  components: { Entry }
}
</script>

<style scoped>
a {
    color: #1c75bc;
}
</style>