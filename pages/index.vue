<template>
  <div>
    <div class="hero container-inner mx-auto flex flex-col sm:flex-row justify-between">
      <div class="text-4xl font-bold w-full sm:w-3/5 text-center sm:text-left mt-12">
        <div class="leading-tight">¡Hola!<br> I'm Jesús Velázquez,</div>
        <div class="text-blue-700 leading-tight">an electrical engineer and software developer</div>
      </div>
      <div class="mt-8 text-center">
        <!--<g-image src="./logos/logo.svg" alt="hero" class="mx-auto sm:mx-0" />-->
        <div class="w-full">
          <img class="w-1/2 mx-auto rounded-full" src="images/avatar.png" />
          <div class="flex justify-center items-center mt-2">
            <a href="mailto:tepexic@tepexic.com" target="_blank" class="p-1">
              <svg class="icon" xmlns="http://www.w3.org/2000/svg" width="45" height="45" viewBox="0 0 24 24"><path d="M12 2.02c5.514 0 10 4.486 10 10s-4.486 10-10 10-10-4.486-10-10 4.486-10 10-10zm0-2c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm0 12.55l-5.992-4.57h11.983l-5.991 4.57zm0 1.288l-6-4.629v6.771h12v-6.771l-6 4.629z"/></svg>
            </a>
            <a href="https://www.linkedin.com/in/jesusavelazquez" target="_blank" class="p-1">
              <svg class="icon" xmlns="http://www.w3.org/2000/svg" width="45" height="45" viewBox="0 0 24 24"><path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm-2 16h-2v-6h2v6zm-1-6.891c-.607 0-1.1-.496-1.1-1.109 0-.612.492-1.109 1.1-1.109s1.1.497 1.1 1.109c0 .613-.493 1.109-1.1 1.109zm8 6.891h-1.998v-2.861c0-1.881-2.002-1.722-2.002 0v2.861h-2v-6h2v1.093c.872-1.616 4-1.736 4 1.548v3.359z"/></svg>
            </a>
            <a href="https://github.com/Tepexic" target="_blank" class="p-1">
              <svg class="icon" xmlns="http://www.w3.org/2000/svg" width="45" height="45" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
            </a>
            <a href="https://twitter.com/tepexic" target="_blank" class="p-1">
              <svg class="icon" xmlns="http://www.w3.org/2000/svg" width="45" height="45" viewBox="0 0 24 24"><path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm6.066 9.645c.183 4.04-2.83 8.544-8.164 8.544-1.622 0-3.131-.476-4.402-1.291 1.524.18 3.045-.244 4.252-1.189-1.256-.023-2.317-.854-2.684-1.995.451.086.895.061 1.298-.049-1.381-.278-2.335-1.522-2.304-2.853.388.215.83.344 1.301.359-1.279-.855-1.641-2.544-.889-3.835 1.416 1.738 3.533 2.881 5.92 3.001-.419-1.796.944-3.527 2.799-3.527.825 0 1.572.349 2.096.907.654-.128 1.27-.368 1.824-.697-.215.671-.67 1.233-1.263 1.589.581-.07 1.135-.224 1.649-.453-.384.578-.87 1.084-1.433 1.489z"/></svg>
            </a>
          </div>
        </div>
      </div>
    </div> <!-- end hero -->

      <!--icons by https://iconmonstr.com/ -->
    <!-- About Me -->
    <div class="container-inner mx-auto py-16" id="about">
      <p class="text-lg sm:text-xl text-justify"> I'm based in Mexico (UTC-5). When I'm away from keyboard, I like to cook, play football,
        brew something (mead, beer, coffee) or get some home improvement done. I'm into Sci-Fi and fantasy novels,
        movies, videogames and TV shows. <br>
      </p>
      <p class="text-lg sm:text-xl text-center">
        <a href="/CV_JesusVelazquez.pdf" target="_blank" class="cv">
          Here's a PDF version of my CV (92kb)
        </a>
      </p>
    </div>

    <div class="overflow-x-hidden">
      <div class="projects container-inner mx-auto text-xl border-t border-gray-500 border-b py-16 mb-16 relative">
        <p class="text-lg sm:text-xl mb-6">
          <span class="font-semibold">These are some of the technologies I've worked with:</span>
        </p>
        <div class="grid grid-cols-3 gap-4 mt-3">
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/html.svg" alt="HTML 5">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/css.svg" alt="CSS 3">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/js.svg" alt="Javascript">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/vue.svg" alt="VueJS">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/react.svg" alt="ReactJS">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/node.png" alt="NodeJS">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/electron.svg" alt="ElectronJS">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/plotly.svg" alt="Plotly">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/bootstrap.svg" alt="Bootstrap">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/tailwind.svg" alt="TailwindCSS">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/git.svg" alt="Git">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/github.png" alt="GitHub">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/python.svg" alt="Python">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img src="images/tech-logos/matlab.png" alt="Matlab">
          </div>
          <div class="w-16 mx-auto flex items-center">
            <img v-if="theme === 'theme-light'" src="images/tech-logos/latex.svg" alt="Latex">
            <img v-else src="images/tech-logos/latex-dark.svg" alt="Latex">
          </div>
        </div>
      </div>
    </div>

    <!-- ======= Footer ======= -->
    <footer class="bg-background-tertiary text-copy-secondary px-4">
      <div class="container mx-auto flex flex-col sm:flex-row items-center justify-between py-8">
        <div class="mb-8 sm:mb-0">
          México, 2020.
        </div>
        <ul class="flex items-center space-x-8">
          <li>
            <a href="mailto:tepexic@tepexic.com" target="_blank">
              <svg class="icon" xmlns="http://www.w3.org/2000/svg" width="45" height="45" viewBox="0 0 24 24"><path d="M12 2.02c5.514 0 10 4.486 10 10s-4.486 10-10 10-10-4.486-10-10 4.486-10 10-10zm0-2c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm0 12.55l-5.992-4.57h11.983l-5.991 4.57zm0 1.288l-6-4.629v6.771h12v-6.771l-6 4.629z"/></svg>
            </a>
          </li>
          <li>
            <a href="https://www.linkedin.com/in/jesusavelazquez" target="_blank">
              <svg class="icon" xmlns="http://www.w3.org/2000/svg" width="45" height="45" viewBox="0 0 24 24"><path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm-2 16h-2v-6h2v6zm-1-6.891c-.607 0-1.1-.496-1.1-1.109 0-.612.492-1.109 1.1-1.109s1.1.497 1.1 1.109c0 .613-.493 1.109-1.1 1.109zm8 6.891h-1.998v-2.861c0-1.881-2.002-1.722-2.002 0v2.861h-2v-6h2v1.093c.872-1.616 4-1.736 4 1.548v3.359z"/></svg>
            </a>
          </li>
          <li>
            <a href="https://github.com/Tepexic" target="_blank">
              <svg class="icon" xmlns="http://www.w3.org/2000/svg" width="45" height="45" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
            </a>
          </li>
            <a href="https://twitter.com/tepexic" target="_blank">
              <svg class="icon" xmlns="http://www.w3.org/2000/svg" width="45" height="45" viewBox="0 0 24 24"><path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm6.066 9.645c.183 4.04-2.83 8.544-8.164 8.544-1.622 0-3.131-.476-4.402-1.291 1.524.18 3.045-.244 4.252-1.189-1.256-.023-2.317-.854-2.684-1.995.451.086.895.061 1.298-.049-1.381-.278-2.335-1.522-2.304-2.853.388.215.83.344 1.301.359-1.279-.855-1.641-2.544-.889-3.835 1.416 1.738 3.533 2.881 5.92 3.001-.419-1.796.944-3.527 2.799-3.527.825 0 1.572.349 2.096.907.654-.128 1.27-.368 1.824-.697-.215.671-.67 1.233-1.263 1.589.581-.07 1.135-.224 1.649-.453-.384.578-.87 1.084-1.433 1.489z"/></svg>
            </a>
        </ul>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  props: {
    theme: {
      type: String,
    }
  },
}
</script>

<style>

</style>