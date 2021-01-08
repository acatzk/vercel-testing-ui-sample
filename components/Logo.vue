<template>
  <svg  :class="`${classes}`"
        viewBox="0 0 116 100"
        fill="#000"
        xmlns="http://www.w3.org/2000/svg">
    <path fill-rule="evenodd" clip-rule="evenodd" d="M57.5 0L115 100H0L57.5 0z"></path>
  </svg>
</template>

<script>
  export default {
    props: {
      classes: {
        type: String,
        required: true,
        default: 'w-10 h-10'
      }
    }
  }
</script>