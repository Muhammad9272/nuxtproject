<template>
  <div class="mt-6 -mb-1 flex flex-wrap">
    <template v-for="(link, key) in links">
      <div v-if="link.url === null" :key="key" class="mr-1 mb-1 px-4 py-3 text-sm border rounded text-gray-400" :class="{ 'ml-auto': link.label === 'Next' }">{{ link.label }}</div>
      <nuxt-link v-else :key="key" class="mr-1 mb-1 px-4 py-3 text-sm border rounded hover:bg-white focus:border-indigo-500 focus:text-indigo-500" :class="{ 'bg-white text-teal-300': link.active, 'ml-auto': link.label === 'Next' }" :to="link.url">{{ link.label }}</nuxt-link>
    </template>
  </div>
</template>

<script>
export default {
  props: {
    links: Array,
  }
}
</script>
<style scoped>
.nuxt-link-exact-active {
  color: #0ef884;
}
</style>
