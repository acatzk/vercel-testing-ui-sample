<template>
  <div>
    <div class=" bg-white border-b border-gray-200">
      <div class="max-w-5xl mx-auto px-6 pt-12 pb-24 flex items-center justify-between">
        <div class="flex space-x-8">
          <div class="flex-shrink-0">
            <Avatar :className="`w-24 h-24`" :src="image" alt="avatar"/>
          </div>
          <div class="flex items-center justify-center">
            <div class="flex items-center space-x-4">
              <h1 class="text-4xl leading-10 font-medium">Joshua Galit</h1>
              <span class="mt-1 text-xs leading-4 text-black font-normal rounded-full uppercase border border-gray-300 px-1 tracking-tight">
                Hobby
              </span>
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
        src: 'https://vercel.com/api/www/avatar/b6157ae57b5655cf0e3390913e459186988a22e5?s=204',
        projects: [
          {
            id: 1,
            title: 'workcation',
            domain: 'workcation.vercel.app',
            devDomain: 'workcation-kacgsrksp.vercel.app',
            githubRepo: 'acatzk/workcation',
            created_at: '25m',
            updated_at: '25m'
          },
          {
            id: 2,
            title: 'meetup',
            domain: 'meetup-beta.vercel.app',
            devDomain: 'meetup-pxearr8h6.vercel.app',
            githubRepo: 'acatzk/meetup',
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