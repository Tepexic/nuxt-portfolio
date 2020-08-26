<template>
  <div class="">
    <div class="md:text-xl mt-8 pt-2 pb-4 border-t-2 border-blue-500 border-opacity-75"> Other articles you might be interested in:
    </div>
    <div class="flex justify-between">
      <NuxtLink
        v-if="prev"
        :to="{ name: 'blog-slug', params: { slug: prev.slug } }"
        class="text-primary font-bold hover:underline"
      >
        {{ prev.title }}
      </NuxtLink>
      <span v-else>&nbsp;</span>
      <NuxtLink
        v-if="next"
        :to="{ name: 'blog-slug', params: { slug: next.slug } }"
        class="font-bold hover:underline"
      >
        {{ next.title }}
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