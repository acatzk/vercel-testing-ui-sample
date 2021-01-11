<template>
  <div>
    <div class=" bg-white border-b border-gray-200">
      <div class="max-w-5xl mx-auto px-6 pt-12 pb-24 flex items-start justify-between">
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
                    <svg class="w-4 h-4"  stroke="none" fill="currentColor" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" preserveAspectRatio="xMidYMid meet" x="3082" data-attributes-set=",xmlns,viewBox,preserveAspectRatio,x"><title xmlns="http://www.w3.org/2000/svg">GitHub icon</title><path xmlns="http://www.w3.org/2000/svg" d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"></path></svg>
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
      </div>
    </div>

    <section class="-mt-10 max-w-5xl mx-auto px-6 grid col-gap-20 grid-cols-12">
      <div class="col-span-7">
        <h2 class="sr-only">Recent Projects</h2>
        <div class="space-y-12 pb-12">
          <ul class="space-y-12">
            <li v-for="(project, i) in projects" :key="i">
              <ProjectCard :project="project"/>
            </li>
          </ul>
          <div>
            <a class="text-sm leading-5 font-bold text-blue-500 hover:underline" href="#">
              View All Projects
            </a>
          </div>
        </div>
      </div>
      <div class="col-span-5 space-y-8">
        <h2 class="text-sm font-semibold mt-2">Recent Activity</h2>
        <ul class="divide-y divide-gray-200">
          <li class="py-2" v-for="r in 32" :key="r">
            <RecentLog />
          </li>
        </ul>
        <div>
          <a class="text-sm leading-5 font-bold text-blue-500 hover:underline" href="#">
            View All Projects
          </a>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
  export default {
    head () {
      return {
        title: 'Dashboard - Vercel'
      }
    },
    components: {
      Avatar: () => import('@/components/Avatar'),
      ProjectCard: () => import('@/components/ProjectCard'),
      RecentLog: () => import('@/components/RecentLog')
    },
    data () {
      return {
        src: require('@/assets/images/avatar.jpg'),
        projects: [
          {
            id: 1,
            title: 'nuxt-vercel-design',
            domain: 'vercel.app.com',
            devDomain: 'vercel-ui-redesign-51pzp1m88.now.sh',
            githubRepo: 'acatzk/vercel',
            created_at: '204d',
            updated_at: '6d'
          },
          {
            id: 2,
            title: 'nuxt-resolute-design',
            domain: 'resolute.app.com',
            devDomain: 'resolute-ui-redesign-51pzp1m88.now.sh',
            githubRepo: 'acatzk/resolute',
            created_at: '03d',
            updated_at: '2d'
          },
          {
            id: 3,
            title: 'nuxt-meetup-design',
            domain: 'meetup.app.com',
            devDomain: 'meetup-ui-redesign-51pzp1m88.now.sh',
            githubRepo: 'acatzk/meetup',
            created_at: '42d',
            updated_at: '2d'
          },
          {
            id: 4,
            title: 'vue-coinbase-design',
            domain: 'coinbase.app.com',
            devDomain: 'coinbase-ui-redesign-51pzp1m88.now.sh',
            githubRepo: 'acatzk/coinbase',
            created_at: '6d',
            updated_at: '3d'
          },
          {
            id: 5,
            title: 'vue-discord-design',
            domain: 'discord.app.com',
            devDomain: 'discord-ui-redesign-51pzp1m88.now.sh',
            githubRepo: 'acatzk/discord',
            created_at: '7d',
            updated_at: '8d'
          },
          {
            id: 6,
            title: 'vue-workacation-design',
            domain: 'workacation.app.com',
            devDomain: 'workacation-ui-redesign-51pzp1m88.now.sh',
            githubRepo: 'acatzk/workacation',
            created_at: '9d',
            updated_at: '3d'
          },
          {
            id: 7,
            title: 'slsu-freedom-wall',
            domain: 'slsu-freedom-wall.app.com',
            devDomain: 'slsu-freedom-wall-ui-redesign-51pzp1m88.now.sh',
            githubRepo: 'acatzk/slsu-freedom-wall',
            created_at: '2d',
            updated_at: '5d'
          },
        ]
      }
    },
    computed: {
      image () {
        return this.src
      }
    }
  }
</script>