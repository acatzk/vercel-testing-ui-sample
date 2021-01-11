<template>
  <div class="relative">
    <span class="inline-flex items-center space-x-2 text-sm leading-5 font-medium">
      <nuxt-link to="/" class="inline-flex items-center space-x-2">
        <span class="flex-shrink-0">
          <Avatar :src="image" :alt="`avatar`"/>
        </span>
        <span>Joshua Galit</span>
      </nuxt-link>
      <span class="hidden sm:block">
        <button @click.prevent="toggle = !toggle" 
                :class="toggle ? 'text-gray-700 border border-gray-100 bg-gray-100' : 'text-gray-400 border bg-transparent border-transparent'"
                class="focus:outline-none border-transparent hover:border-gray-200 hover:bg-gray-100 rounded transition ease-in-out duration-150">
          <svg class="w-5 h-5" fill="currentColor" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" preserveAspectRatio="xMidYMid meet"><path xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" d="M10 3a1 1 0 01.707.293l3 3a1 1 0 01-1.414 1.414L10 5.414 7.707 7.707a1 1 0 01-1.414-1.414l3-3A1 1 0 0110 3zm-3.707 9.293a1 1 0 011.414 0L10 14.586l2.293-2.293a1 1 0 011.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
        </button>
      </span>
    </span>
    <div :class="`${toggle ? 'block' : 'hidden'}`">
      <button @click="toggle = false" class="cursor-default fixed block inset-0 w-full h-full focus:outline-none"></button>
      <div v-show="toggle" class="absolute bg-white shadow-lg w-56 rounded-md overflow-hidden divide-y divide-gray-200">
        <div class="py-2">
          <div class="pt-3 px-4 pb-3 leading-5 uppercase tracking-wide text-gray-600 text-xs">
            Personal Account
          </div>
          <ul>
            <li class="px-4 py-4">
              <div class="flex items-center justify-between space-x-4">
                <a href="#" class="flex items-center space-x-3 text-sm text-gray-600 transition ease-in-out duration-150 hover:text-black" @click="toggle = false">
                  <Avatar :src="image" :alt="`avatar`" :className="`w-6 h-6`" />
                  <span>Joshua Galit</span>
                </a>
                <div class="text-gray-500" @click="toggle = false">
                  <a href="#" class="transition ease-in-out duration-150 hover:text-black">
                    <svg class="w-5 h-5" fill="currentColor" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" preserveAspectRatio="xMidYMid meet"><path xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" d="M11.49 3.17c-.38-1.56-2.6-1.56-2.98 0a1.532 1.532 0 01-2.286.948c-1.372-.836-2.942.734-2.106 2.106.54.886.061 2.042-.947 2.287-1.561.379-1.561 2.6 0 2.978a1.532 1.532 0 01.947 2.287c-.836 1.372.734 2.942 2.106 2.106a1.532 1.532 0 012.287.947c.379 1.561 2.6 1.561 2.978 0a1.533 1.533 0 012.287-.947c1.372.836 2.942-.734 2.106-2.106a1.533 1.533 0 01.947-2.287c1.561-.379 1.561-2.6 0-2.978a1.532 1.532 0 01-.947-2.287c.836-1.372-.734-2.942-2.106-2.106a1.532 1.532 0 01-2.287-.947zM10 13a3 3 0 100-6 3 3 0 000 6z" clip-rule="evenodd"></path></svg>
                  </a>
                </div>
              </div>
            </li>
          </ul>
        </div>
        <div class="py-2">
          <a href="#" class="py-3 px-4 flex items-center justify-between text-sm leading-5 text-gray-600 transition ease-in-out duration-150 hover:text-black" @click="toggle = false">
            <span>Create Team</span>
            <span>
              <svg class="h-5 w-5" fill="currentColor" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" preserveAspectRatio="xMidYMid meet"><path xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" d="M10 5a1 1 0 011 1v3h3a1 1 0 110 2h-3v3a1 1 0 11-2 0v-3H6a1 1 0 110-2h3V6a1 1 0 011-1z" clip-rule="evenodd"></path></svg>
            </span>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    components: {
      Avatar: () => import('./Avatar')
    },
    data () {
      return {
        src: 'https://vercel.com/api/www/avatar/b6157ae57b5655cf0e3390913e459186988a22e5?s=204',
        toggle: false
      }
    },
    computed: {
      image () {
        return this.src
      }
    },
    mounted() {
      const onEscape = (e) => {
        if (!this.toggle || e.key !== 'Escape') {
          return
        }
        this.toggle = false
      }
      document.addEventListener('keydown', onEscape)
      this.$on('hook:destroyed', () => {
        document.removeEventListener('keydown', onEscape)
      })
    }
  }
</script>