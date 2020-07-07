<template>
  <!-- Navigation -->
  <header class="px-4">
    <nav class="container mx-auto flex flex-col sm:flex-row justify-between items-center py-8">
      <div class="mb-4 sm:mb-0">
          <svg class="h-12 w-12 fill-current" xmlns="http://www.w3.org/2000/svg" width="50" height="50" viewBox="0 0 500 500"><style>.a{fill:none;stroke-width:1px;stroke:#000;}.b{font-family:sans-serif;font-size:300px;letter-spacing:0px;line-height:100%;stroke-width:1px;word-spacing:0px;}</style><defs><clipPath clipPathUnits="userSpaceOnUse"/><clipPath clipPathUnits="userSpaceOnUse"/></defs><g transform="translate(0 -552.36216)"><text x="168.5" y="951.7" style="-inkscape-font-specification:'Times New Roman, ';font-family:'Times New Roman';font-size:500px;letter-spacing:0px;line-height:100%;stroke-width:1px;word-spacing:0px"><tspan x="168.5" y="951.7" dy="2.7678721" dx="2.7678721" style="-inkscape-font-specification:'Times New Roman, ';font-family:'Times New Roman'">  t</tspan></text><text x="-12.4" y="640.1" transform="scale(0.66317841 1.5078899)" class="b"><tspan x="-12.4" y="640.1">  &lt;</tspan></text><text x="-765.1" y="640.4" transform="scale(-0.6631784 1.5078899)" class="b"><tspan x="-765.1" y="640.4">  &lt;</tspan></text></g></svg>
      </div>
      <ul class="uppercase tracking-wide font-bold flex items-center space-x-8">
        <li>
          <a href="#" class="text-copy-primary hover:text-gray-500" @click.prevent="toggleTheme" alt="Change theme">
            <svg v-if="theme === 'theme-light'" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-moon"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/></svg>
            <svg v-else xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-sun"><circle cx="12" cy="12" r="5"/><path d="M12 1v2M12 21v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M1 12h2M21 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"/></svg>
          </a>
        </li>
        <li>
          <router-link to="/" class="text-copy-primary hover:text-gray-500" alt="Go Home">
            Home
          </router-link>
        </li>
        <li>
          <router-link to="/projects" class="text-copy-primary hover:text-gray-500" alt="Go to Projects">
            Projects
          </router-link>
        </li>
        <li>
          <router-link to="/blog" class="text-copy-primary hover:text-gray-500" alt="Go to Blog">
            Blog
          </router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  
  props: {
    theme: {
      type: String,
      required: true,
    }
  },

  methods: {
    toggleTheme() {
      const newTheme = this.theme === 'theme-light' ? 'theme-dark' : 'theme-light'
      localStorage.setItem('theme', newTheme)
      this.$emit('themeChanged', newTheme)
    }
  }
}
</script>

<style>
</style>