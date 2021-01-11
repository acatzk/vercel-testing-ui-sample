<template>
  <header class="bg-white border-b border-gray-200">
    <nav class="max-w-5xl mx-auto flex items-center justify-between mt-4 px-6 flex-wrap">
      <!-- first flex between item -->
      <div class="flex items-center space-x-3">
        <Logo :classes="`h-6`"/>
        <span>
          <svg class="h-8 w-8 text-gray-300" viewBox="0 0 32 32" stroke="currentColor" stroke-width="1"><line x1="10" y1="28" x2="22" y2="4"></line></svg>
        </span>
        <SwitchAccount />
      </div>

      <!-- second flex between item -->
      <div class="flex items-center text-sm text-gray-600 space-x-4">
        <div class="hidden sm:block">
          <div class="flex items-center space-x-5">
            <button type="button" class="leading-5 border border-gray-200 rounded-md px-3 py-1 focus:outline-none focus:shadow-sm hover:border-black transition ease-in-out duration-150">
              Feedback
            </button>
            <nuxt-link to="/" class="leading-5 hover:text-black transition ease-in-out duration-150">
              Changelog
            </nuxt-link>
            <nuxt-link to="/" class="leading-5 hover:text-black transition ease-in-out duration-150">
              Support
            </nuxt-link>
            <nuxt-link to="/" class="leading-5 hover:text-black transition ease-in-out duration-150">
              Docs
            </nuxt-link>
            <button type="button" class="flex-shrink-0">
              <Avatar :src="src" :alt="`avatar`"/>
            </button>
          </div>
        </div>
        <div class="block sm:hidden">
          <button>
            <svg class="w-8 h-8 text-gray-700" stroke="currentColor" fill="none" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" preserveAspectRatio="xMidYMid meet" data-attributes-set=",xmlns:xlink,xmlns,viewBox,preserveAspectRatio"><path xmlns="http://www.w3.org/2000/svg" stroke-linecap="round" stroke-linejoin="round" stroke-width="0.5" d="M4 8h16M4 16h16"></path></svg>
          </button>
        </div>
      </div>

    </nav>
  
    <nav class="max-w-5xl leading-5 mx-auto mt-4">
      <ul class="text-sm flex items-center space-x-4 px-6 overflow-y-auto">
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
      Avatar: () => import('./Avatar'),
      SwitchAccount: () => import('./SwitchAccount')
    },
    data () {
      return {
        src: 'https://vercel.com/api/www/avatar/b6157ae57b5655cf0e3390913e459186988a22e5?s=204',
        links: ['Overview', 'Projects', 'Integrations', 'Activity', 'Domains', 'Usage', 'Settings'],
        setLink: 'Overview'
      }
    }
  }
</script>