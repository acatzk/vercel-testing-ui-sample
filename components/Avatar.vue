<template>
  <img  class="w-8 h-8 rounded-full border border-gray-200 object-cover" 
        :src="image" 
        :alt="alt" 
        :class="`${className}`"/>
</template>

<script>
  export default {
    props: {
      src: {
        type: String,
        required: true
      },
      alt: {
        type: String,
        required: true
      },
      className: {
        type: String,
        required: false
      }
    },
    computed: {
      image () {
        return this.src
      }
    }
  }
</script>