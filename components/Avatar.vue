<template>
  <img  class="rounded-full border border-gray-200 object-cover" 
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
        required: false,
        default: 'w-8 h-8 '
      }
    },
    computed: {
      image () {
        return this.src
      }
    }
  }
</script>