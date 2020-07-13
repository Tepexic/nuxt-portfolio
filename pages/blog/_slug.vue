<template>
  <article class="container md:container-inner mx-auto" >

    <div class="text-white shadow-lg w-full bg-fixed" v-bind:style="{ 'background-image': 'url(' + article.img + ')' }">
      <div class="mt-8 flex uppercase text-sm justify-end px-4 bg-gray-800 bg-opacity-75">
        <p class="mr-3">
          {{ formatDate(article.createdAt) }}
        </p>
        <span class="mr-3">•</span>
        <p>{{ article.author.name }}</p>
      </div>
      <h1 class="text-6xl font-bold pl-2 bg-gray-800 bg-opacity-50">{{ article.title }}</h1>
    </div>

    <div class="mt-4 px-4 md:px-16">
      <h1 class="font-bold text-4xl">{{ article.title }}</h1>
      <p class="italic">{{ article.description }}</p>
      <p class="pb-4 text-xs uppercase">Post last updated: {{ formatDate(article.updatedAt) }}</p>

      <!-- table of contents -->
      <nav class="pb-6">
        <h2 class="pt-4">Contents:</h2>
          <ul class="toc"
            <li v-for="link of article.toc" :key="link.id" :class="{'font-semibold': link.depth === 2}">
              <nuxtLink :to="`#${link.id}`" class="hover:underline" :class="{'py-2': link.depth === 2, 'ml-2 pb-2': link.depth === 3}">
                {{ link.text }}
              </nuxtLink>
            </li>
          </ul>
      </nav>

      <!-- content from markdown -->
      <nuxt-content class="" :document="article" />
      <!-- 
      <author :author="article.author" />
      
      <PrevNext :prev="prev" :next="next" class="mt-8" />-->
    </div>
  </article>
</template>
<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('articles', params.slug).fetch()
    const [prev, next] = await $content('articles')
      .only(['title', 'slug'])
      .sortBy('createdAt', 'asc')
      .surround(params.slug)
      .fetch()
    return {
      article,
      prev,
      next
    }
  },
  methods: {
    formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    }
  }
}
</script>
<style>
.toc {
  @apply list-disc;
  @apply list-inside;
}

.nuxt-content p {
  margin-bottom: 20px;
}
.nuxt-content h2 {
  font-weight: bold;
  font-size: 28px;
}
.nuxt-content h3 {
  font-weight: bold;
  font-size: 22px;
}
.nuxt-content h1 {
  @apply font-semibold;
  @apply leading-relaxed;
  @apply my-8;
  @apply text-4xl;
}
.nuxt-content ul {
  @apply my-2;
}
.nuxt-content li {
  @apply list-disc;
  @apply list-inside;
}
.nuxt-content pre {
  @apply px-4;
}
.nuxt-content code {
  @apply p-4;
}
.nuxt-content table {
  @apply table-auto;
}
.nuxt-content th {
  @apply font-semibold;
  @apply mb-4;
}
.nuxt-content td {
  @apply py-2;
  @apply px-4;
}
.nuxt-content a {
  @apply font-semibold;
  @apply text-blue-500;
}
.nuxt-content a:hover {
  @apply font-bold;
  @apply text-blue-400;
}
.nuxt-content img {
  @apply mt-4;
  @apply rounded-lg;
  @apply shadow-lg;
  @apply border-2;
  @apply border-gray-300;
  @apply m-auto;
  @apply bg-gray-400;
  @apply h-48;
}
</style>
