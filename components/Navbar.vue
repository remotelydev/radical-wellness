<template>
  <header
    :class="isOpen ? 'bg-white' : 'bg-transparent'"
    class="container fixed inset-x-0 z-10 sm:flex sm:justify-between sm:items-center"
  >
    <div class="flex justify-between items-center p-2">
      <div>
        <nuxt-link
          class="font-bold px-2 py-1"
          to="/"
          @click.native="isOpen = false"
          >Radical Wellness</nuxt-link
        >
      </div>
      <div class="sm:hidden">
        <button type="button" @click="isOpen = !isOpen">
          <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
            <path
              v-if="isOpen"
              fill-rule="evenodd"
              d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1 1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828 4.829 4.828 4.828z"
            />
            <path
              v-if="!isOpen"
              fill-rule="evenodd"
              d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
            />
          </svg>
        </button>
      </div>
    </div>
    <div :class="isOpen ? 'block' : 'hidden'" class="px-2 pt-2 pb-4 sm:flex">
      <nuxt-link
        class="block px-2 py-1 rounded hover:bg-gray-200"
        to="/shop"
        @click.native="isOpen = false"
        >Shop</nuxt-link
      >
      <nuxt-link
        class="block px-2 py-1 rounded hover:bg-gray-200"
        to="/cards"
        @click.native="isOpen = false"
        >Cards</nuxt-link
      >
      <nuxt-link
        class="block px-2 py-1 rounded hover:bg-gray-200"
        to="/contact"
        @click.native="isOpen = false"
        >Contact</nuxt-link
      >
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    }
  }
}
</script>

<style scoped>
a {
  @apply text-black no-underline;
}
a:hover {
  @apply underline;
}
</style>
