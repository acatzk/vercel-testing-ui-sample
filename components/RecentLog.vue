<template>
  <div class="flex items-center justify-between text-sm text-gray-600">
    <div class="flex items-center space-x-4">
      <Avatar :src="src" :alt="`avatar`"/>
      <span class="space-x-1">
        <a class="text-black hover:underline" href="#">You</a> 
        <span>logged in via GitHub</span>
      </span>
    </div>
    <span>26d</span>
  </div>
</template>

<script>
  export default {
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