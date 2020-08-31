<template>
  <div class="mb-2">
    <div class="mt-8 pt-2 pb-4 border-t-2 border-blue-500 border-opacity-75">
    </div>
    <div class="md:flex md:justify-between">
      <NuxtLink
        v-if="prev"
        :to="{ name: 'blog-slug', params: { slug: prev.slug } }"
        class="py-2 px-6 m-2 rounded md:shadow"
      >
        <div class="flex items-center mb-2">
          <svg class="w-6 mr-2" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18" />
          </svg>
          <div>Previous</div>
        </div>
        <div class="text-primary font-bold hover:underline"> {{ prev.title }} </div>
      </NuxtLink>
      <span v-else>&nbsp;</span>
      <NuxtLink
        v-if="next"
        :to="{ name: 'blog-slug', params: { slug: next.slug } }"
        class="py-2 px-4 m-2 rounded md:shadow"
      >
        <div class="flex items-center mb-2">
          <svg class="w-6 mr-2" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
          </svg>
          <div>Next</div>
        </div>
        <div class="text-primary font-bold hover:underline"> {{ next.title }} </div>
      </NuxtLink>
      <span v-else>&nbsp;</span>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      prev: {
        type: Object,
        default: () => null
      },
      next: {
        type: Object,
        default: () => null
      }
    }
  }
</script>