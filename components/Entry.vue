<template>
<article class="w-full lg:flex my-4 shadow-lg">
  <div class="h-48 lg:h-auto lg:w-48 flex-none bg-cover rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden"
    v-bind:style="{ backgroundImage: 'url(' + hero + ')' }"
    :title="title">
  </div>

  <div class="border-r border-b border-l border-grey-light lg:border-l-0 lg:border-t lg:border-grey-light rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal">
    <div class="mb-8">
      <!--title-->
      <nuxt-link :to="'/blog/' + link">
        <div class="font-bold text-xl mb-2 text-blue-600">{{ title }}</div>
      </nuxt-link>
      <!--description-->
      <p class="text-base">{{ description }}</p>
    </div>
    <!--author/date-->
    <div class="flex items-center mt-4  mb-2 justify-between">
        <div class="flex items-center">
            <svg class="h-3 w-3 fill-current mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M12.3 3.7l4 4L4 20H0v-4L12.3 3.7zm1.4-1.4L16 0l4 4-2.3 2.3-4-4z"/></svg>
            <div class="mt-1 text-right text-xs mr-4">
            By {{author}}
            </div>
        </div>
        <div class="flex items-center">
            <svg class="h-4 w-4 fill-current mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M1 4c0-1.1.9-2 2-2h14a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V4zm2 2v12h14V6H3zm2-6h2v2H5V0zm8 0h2v2h-2V0zM5 9h2v2H5V9zm0 4h2v2H5v-2zm4-4h2v2H9V9zm0 4h2v2H9v-2zm4-4h2v2h-2V9zm0 4h2v2h-2v-2z"/></svg>
            <div class="mt-1 text-right text-xs">
            {{ date }}
            </div>
        </div>
    </div>
  </div>
</article>
</template>

<script>
export default {
  name: 'Entry',

  data: function () {
    return {
      colors: {
        "resources": "orange",
        "webdev": "indigo",
        "hosting": "purple",
        "javascript": "pink",
        "Vue": "green",
        "React": "teal",
      }
    }
  },

  props: {
    title: {
      type: String,
      default: 'Blog post'
    },
    author: {
      type: String,
      default: 'Tepexic'
    },
    date: {
      type: String,
      default: 'January 1st, 2020'
    },
    description: {
      type: String,
      default: 'A new blogpost'
    },
    link: {
      type: String,
      default: '/blog'
    },
    tags: {
      type: Array,
      default: () => {["Post","resources", "webdev", "hosting","Post","resources", "webdev", "hosting"]},
    },
    hero: {
      type: String,
      default: "https://picsum.photos/32/32/?random"
    }
  },
}
</script>

<style scoped>
</style>
