<template>
  <div class="divide-y divide-gray-200 rounded-lg bg-white shadow-md overflow-hidden">
    <div class="p-6 space-y-3">
      <div class="flex items-center justify-between">
        <h3 class="font-medium text-2xl">{{ project.title }}</h3>
        <button class="py-1 px-5 border border-gray-300 rounded text-sm 
                        transition ease-in-out duration-150 text-gray-700 
                      hover:border-black hover:text-black">
              Visit
        </button>
      </div>
      <div class="space-y-1">
        <div class="space-x-2" aria-label="Production deployment">
          <a class="space-x-1  text-sm font-normal leading-5" href="#">
            <span class="mt-1 inline-block h-2 w-2 rounded-full bg-green-300" aria-hidden></span>
            <span>{{ project.domain }}</span>
          </a>
          <span class="text-xs font-normal leading-4 px-2 py-1 border border-gray-300 rounded-full bg-gray-100">
            Production
          </span>
          <span class="text-sm text-gray-600 leading-5 tracking-wide">{{ project.created_at }}</span>
        </div>

        <div class="space-x-1" aria-label="Production deployment">
          <a class="space-x-1  text-sm font-normal leading-5" href="#">
            <span class="mt-1 inline-block h-2 w-2 rounded-full bg-green-300" aria-hidden></span>
            <span>{{ project.devDomain }}</span>
          </a>
          <span class="text-xs font-normal leading-4 px-2 py-1 border border-gray-300 rounded-full bg-gray-100">
            Latest
          </span>
          <span class="text-sm text-gray-600 leading-5 tracking-wide">{{ project.updated_at }}</span>
        </div>
      </div>
    </div>
    <div class="px-6 py-3">
      <a href="#" class="inline-flex items-center space-x-2 text-sm leading-5 font-medium">
        <span>
          <svg class="w-4 h-4" stroke="none" fill="currentColor" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" preserveAspectRatio="xMidYMid meet" x="3082" data-attributes-set=",xmlns,viewBox,preserveAspectRatio,x"><title xmlns="http://www.w3.org/2000/svg">GitHub icon</title><path xmlns="http://www.w3.org/2000/svg" d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"></path></svg>
        </span>
        <span class="tracking-wide font-medium">{{ project.githubRepo }}</span>
      </a>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      project: {
        type: Object,
        required: true
      }
    }
  }
</script>