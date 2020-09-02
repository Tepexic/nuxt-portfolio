<template>
<section class="w-full lg:flex my-8 shadow-lg">
  <div class="h-56 lg:h-auto lg:w-56 flex-none bg-cover rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden"
    v-bind:style="{ backgroundImage: 'url(' + hero + ')' }"
    :title="title">
  </div>

  <div class="rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal">
    <div class="mb-8">
      <!--title-->
      <div class="font-bold text-xl mb-2 text-blue-600">
        <a :href="link" target="_blank">{{ title }} </a>
      </div>
      <!--technologies-->
      <div class="mt-2 flex">
        <div
          v-for="t in tecs"
          :key="t"
          class = "text-xs uppercase rounded-full border-2 font-semibold py-1 px-2 mx-1 shadow-md text-center mb-2"
          >
          {{t}}
        </div>
      </div>
      <!--description-->
      <p class="text-base">{{ description }}</p>
    </div>
    <!--github and demo-->
    <div class="flex items-center justify-between">
      <a :href="ghlink" target="_blank"  class="flex items-center mt-4  mb-2 transition duration-150 ease-in-out transform hover:scale-105">
        <svg class="fill-current h-6 mr-2" viewBox="0 0 16 16" fill="currentColor"><path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path></svg>
        <div class="mt-1 text-right text-xs mr-4">
          See on GitHub
        </div>
      </a>
      <a :href="link" target="_blank" class="flex items-center mt-4  mb-2 transition duration-150 ease-in-out transform hover:scale-105">
        <svg class="fill-current h-6 mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M0 4c0-1.1.9-2 2-2h16a2 2 0 0 1 2 2v12a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V4zm6 0v12h8V4H6zM2 5v2h2V5H2zm0 4v2h2V9H2zm0 4v2h2v-2H2zm14-8v2h2V5h-2zm0 4v2h2V9h-2zm0 4v2h2v-2h-2zM8 7l5 3-5 3V7z"/></svg>
        <div class="mt-1 text-right text-xs mr-4">
          Live Demo
        </div>
      </a>
    </div>
  </div>
</section>
</template>

<script>
export default {
  name: 'Project',

  data: function () {
    return {}
  },

  props: {
    title: {
      type: String,
      default: 'Awesome project'
    },
    description: {
      type: String,
      default: 'New sideproject'
    },
    link: {
      type: String,
      default: '/'
    },
    ghlink: {
      type: String,
      default: 'https://github.com/Tepexic'
    },
    tecs: {
      type: Array,
      default: () => {["vue", "node"]},
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
