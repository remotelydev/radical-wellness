<template>
  <div class="container">
    <div>
      <logo />
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
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
