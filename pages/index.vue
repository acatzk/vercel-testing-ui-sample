<template>
  <div class="max-w-7xl mx-auto">
    <section class=" px-16 pt-12 pb-24 bg-white flex items-start justify-between border-b border-gray-300">
      <div class="flex space-x-8">
        <div class="flex-shrink-0">
          <Avatar :className="`w-24 h-24`" :src="image" alt="avatar"/>
        </div>
        <div class="flex flex-col justify-between space-y-4">
          <div class="flex items-center space-x-4">
            <h1 class="text-3xl leading-10 font-bold">Joshua Galit</h1>
            <span class="mt-1 text-xs leading-4 text-black font-medium rounded-full uppercase border border-gray-200 bg-gray-200 px-1 tracking-wide">
              Hobby
            </span>
          </div>
          <div>
            <dl>
              <dt class="text-xs leading-5 text-gray-500 uppercase tracking-wide font-medium">
                Git integration
              </dt>
              <dd class="flex items-center space-x-2 text-sm leading-5 font-medium">
                <span>
                  <svg class="w-4 h-4 rounded-full" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" preserveAspectRatio="xMidYMid meet"><path xmlns="http://www.w3.org/2000/svg" d="M20.222 0c1.406 0 2.54 1.137 2.607 2.475V24l-2.677-2.273-1.47-1.338-1.604-1.398.67 2.205H3.71c-1.402 0-2.54-1.065-2.54-2.476V2.48C1.17 1.142 2.31.003 3.715.003h16.5L20.222 0zm-6.118 5.683h-.03l-.202.2c2.073.6 3.076 1.537 3.076 1.537-1.336-.668-2.54-1.002-3.744-1.137-.87-.135-1.74-.064-2.475 0h-.2c-.47 0-1.47.2-2.81.735-.467.203-.735.336-.735.336s1.002-1.002 3.21-1.537l-.135-.135s-1.672-.064-3.477 1.27c0 0-1.805 3.144-1.805 7.02 0 0 1 1.74 3.743 1.806 0 0 .4-.533.805-1.002-1.54-.468-2.14-1.404-2.14-1.404s.134.066.335.2h.06c.03 0 .044.015.06.03v.006c.016.016.03.03.06.03.33.136.66.27.93.4a8.18 8.18 0 001.8.536c.93.135 1.996.2 3.21 0 .6-.135 1.2-.267 1.8-.535.39-.2.87-.4 1.397-.737 0 0-.6.936-2.205 1.404.33.466.795 1 .795 1 2.744-.06 3.81-1.8 3.87-1.726 0-3.87-1.815-7.02-1.815-7.02-1.635-1.214-3.165-1.26-3.435-1.26l.056-.02zm.168 4.413c.703 0 1.27.6 1.27 1.335 0 .74-.57 1.34-1.27 1.34-.7 0-1.27-.6-1.27-1.334.002-.74.573-1.338 1.27-1.338zm-4.543 0c.7 0 1.266.6 1.266 1.335 0 .74-.57 1.34-1.27 1.34-.7 0-1.27-.6-1.27-1.334 0-.74.57-1.338 1.27-1.338z"></path></svg>
                </span>
                <span>acatzk</span>
              </dd>
            </dl>
          </div>
        </div>
      </div>
      <div class="grid grid-cols-2 col-gap-5">
        <button type="button" 
                class="`inline-flex text-sm leading-5 px-6 py-2 tracking-wide
                        rounded-md border transition ease-in-out duration-150 
                      text-gray-700 hover:border-black hover:text-black `">
          Invite Team
        </button>
        <button type="button" 
                class="`inline-flex text-sm leading-5 px-6 py-2 rounded-md border border-black 
                        tracking-wide transition ease-in-out duration-150
                      bg-black text-white hover:bg-white hover:text-black `">
          Import Project
        </button>
      </div>
    </section>
    
  </div>
</template>

<script>
  export default {
    head () {
      return {
        title: 'Vercel'
      }
    },
    components: {
      Avatar: () => import('@/components/Avatar')
    },
    data () {
      return {
        src: require('@/assets/images/avatar.jpg')
      }
    },
    computed: {
      image () {
        return this.src
      }
    }
  }
</script>