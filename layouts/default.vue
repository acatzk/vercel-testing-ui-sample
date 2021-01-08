<template>
  <div class="font-sans bg-gray-100 antialiased min-h-screen h-full">
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