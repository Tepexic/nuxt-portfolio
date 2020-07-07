<template>
  <div class="my-6 shadow-lg rounded-lg lg:my-10 lg:py-4 lg:px-8">
    <div class="sm:flex-wrap md:flex">
      <img class="w-full object-cover rounded-t-lg md:w-5/12 md:rounded-lg lg:w-3/12 lg:rounded-lg xl:w-3/12 xl:rounded-lg"
        :alt="title"
        :src="hero">

      <div class="w-full pb-2 px-2 md:w-7/12 md:py-2 md:pl-4 md:pr-2 lg:w-9/12 xl:w-9/12">
        <!--title-->
        <router-link :to="'/blog/' + link" class="text-3xl font-semibold text-blue-700 leading-relaxed text-center">
          {{ title }}
        </router-link>
        <!--tags-->
        <div class="mt-2 flex">
          <div
            v-for="t in tags"
            :key="t"
            class = "text-xs uppercase rounded-full border-2 font-semibold py-1 px-2 mx-1 shadow-md text-center mb-2"
            >
            {{t}}
          </div>
        </div>
        <!--description-->
        <div class="mt-2">
          {{ description }}
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
    </div>
</div>
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

<style>

</style>
