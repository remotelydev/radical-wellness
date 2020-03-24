<template>
  <div class="container">
    <nuxt-link class="w-64 text-black" to="/cards">
      <Logo />
    </nuxt-link>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style scoped>
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
</style>
