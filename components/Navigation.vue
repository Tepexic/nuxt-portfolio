<template>
  <!-- Navigation -->
  <header class="px-4">
    <nav class="container mx-auto flex flex-col sm:flex-row justify-between items-center py-8">
      <div class="mb-4 sm:mb-0">
        <svg class="h-12 w-12 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 500 500"><style>.a{fill:none;stroke-width:1px;stroke:#000;}.b{-inkscape-font-specification:'Times New Roman, ';font-family:'Times New Roman';font-size:500px;letter-spacing:0px;line-height:100%;stroke-width:1px;word-spacing:0px;}.c{font-family:sans-serif;font-size:300px;letter-spacing:0px;line-height:100%;stroke-width:1px;word-spacing:0px;}</style><defs><clipPath clipPathUnits="userSpaceOnUse"/><clipPath clipPathUnits="userSpaceOnUse"/></defs><g transform="translate(0 -552.36216)"><path d="m260 628.2v80.4h57.2v18.7H260v158.7c0 15.9 2.2 26.5 6.7 32.1 4.6 5.5 10.5 8.3 17.6 8.3 5.9 0 11.6-1.8 17.1-5.3 5.5-3.7 9.8-9.2 12.8-16.3h10.4c-6.2 17.5-15 30.6-26.4 39.5-11.4 8.7-23.2 13.1-35.3 13.1-8.2 0-16.2-2.2-24-6.7-7.8-4.6-13.6-11.1-17.4-19.5-3.7-8.5-5.6-21.6-5.6-39.3V727.4h-38.7v-8.8c9.8-3.9 19.8-10.5 29.9-19.8 10.3-9.4 19.5-20.6 27.5-33.4 4.1-6.8 9.8-19.1 17.1-37.1z" class="b"/><text style="font-size:20px;letter-spacing:0px;line-height:100%;word-spacing:0px"><tspan class="b"><tspan style="-inkscape-font-specification:'Times New Roman, ';font-family:'Times New Roman'">  t</tspan></tspan></text><path d="M150.3 658.3 23.1 786.8v31.1L150.3 946.4V901.3L50 802.4 150.3 703.4Z" class="c"/><path d="m353 658.4 127.2 128.5v31.1L353 946.5V901.4L453.3 802.4 353 703.5Z" class="c"/></g></svg>
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