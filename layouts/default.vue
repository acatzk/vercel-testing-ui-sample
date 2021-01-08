<template>
  <div class="font-sans bg-gray-100 antialiased">
    <Header />
    <main>
      <Nuxt />
    </main>
  </div>
</template>

<script>
  export default {
    components: {
      Header: () => import('@/components/Header')
    }
  }
</script>