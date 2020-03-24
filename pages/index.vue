<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        radical-truth
      </h1>
      <h2 class="subtitle">
        Radical truth website
      </h2>
      <div class="links">
        <nuxt-link to="/cards">
          Cards
        </nuxt-link>
      </div>
    </div>
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
