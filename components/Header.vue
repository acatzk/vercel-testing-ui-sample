<template>
  <header class="bg-white border-b border-gray-300">
    <nav class="flex items-center justify-between max-w-7xl mx-auto mt-4 px-6 flex-wrap">
      <!-- first flex between item -->
      <div class="flex items-center space-x-3">
        <Logo :classes="`h-5`"/>
        <span>
          <svg class="h-8 w-8 text-gray-300" viewBox="0 0 32 32" stroke="currentColor" stroke-width="1"><line x1="10" y1="28" x2="22" y2="4"></line></svg>
        </span>
        <span class="inline-flex items-center space-x-2 text-sm leading-5 font-medium">
          <nuxt-link to="/" class="inline-flex items-center space-x-2">
            <span class="flex-shrink-0">
              <Avatar :src="src" :alt="`avatar`"/>
            </span>
            <span>Joshua Galit</span>
          </nuxt-link>
          <span>
            <button class="focus:outline-none border-transparent hover:border-gray-200 hover:bg-gray-100 rounded transition ease-in-out duration-150">
              <svg class="w-5 h-5 text-gray-400" fill="currentColor" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" preserveAspectRatio="xMidYMid meet"><path xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" d="M10 3a1 1 0 01.707.293l3 3a1 1 0 01-1.414 1.414L10 5.414 7.707 7.707a1 1 0 01-1.414-1.414l3-3A1 1 0 0110 3zm-3.707 9.293a1 1 0 011.414 0L10 14.586l2.293-2.293a1 1 0 011.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
            </button>
          </span>
        </span>
      </div>
      <!-- second flex between item -->
      <div class="flex items-center text-sm text-gray-600 space-x-4">
        <div class="flex items-center space-x-5">
          <button type="button" class="leading-5 border border-gray-200 rounded-md px-2 py-1 focus:outline-none focus:shadow-sm hover:border-black transition ease-in-out duration-150">
            Feedback
          </button>
          <nuxt-link to="/" class="leading-5 hover:text-black transition ease-in-out duration-150">
            Blog
          </nuxt-link>
          <nuxt-link to="/" class="leading-5 hover:text-black transition ease-in-out duration-150">
            Support
          </nuxt-link>
          <nuxt-link to="/" class="leading-5 hover:text-black transition ease-in-out duration-150">
            Docs
          </nuxt-link>
        </div>
        <button type="button">
          <svg class="w-5 h-5" fill="currentColor" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" preserveAspectRatio="xMidYMid meet"><path xmlns="http://www.w3.org/2000/svg" d="M6 10a2 2 0 11-4 0 2 2 0 014 0zm6 0a2 2 0 11-4 0 2 2 0 014 0zm4 2a2 2 0 100-4 2 2 0 000 4z"></path></svg>
        </button>
        <button type="button" class="flex-shrink-0">
          <Avatar :src="src" :alt="`avatar`"/>
        </button>
      </div>
    </nav>
  
    <nav class="max-w-7xl leading-5 mx-auto mt-4">
      <ul class="text-sm flex items-center space-x-4 px-6 flex-wrap">
        <li v-for="(link, i) in links" :key="i"
            class="pb-3 transition ease-in-out duration-150 hover:text-black"
            :class="`${link === setLink ? 'border-b-2 border-black text-black' : 'border-b-2 border-transparent text-gray-600'}`"
            @click.prevent="setLink = link">
          <a href="#" class="tracking-wide">{{ link }}</a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
  export default {
    components: {
      Logo: () => import('./Logo'),
      Avatar: () => import('./Avatar')
    },
    data () {
      return {
        src: require('@/assets/images/avatar.jpg'),
        links: ['Overview', 'Projects', 'Integrations', 'Activity', 'Domains', 'Usage', 'Settings'],
        setLink: 'Overview'
      }
    }
  }
</script>