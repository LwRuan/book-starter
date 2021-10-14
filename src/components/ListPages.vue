<script setup lang="ts">
import { useRouter } from 'vue-router'

const router = useRouter()
const routes = router.getRoutes()
  .filter(i => i.path.startsWith('/book') && i.meta.frontmatter)
  .filter(i => !i.path.endsWith('book'))
  .sort((a, b) => (a.path).localeCompare(b.path))

for (const r of routes)
  console.log(r.meta)

</script>
<template>
  <ul>
    <router-link
      v-for="route in routes"
      :key="route.path"
      :to="route.path"
      class="item block mb-2 mt-2"
    >
      <li>
        <div v-if="route.meta.frontmatter.type=='chapter'" class="title font-semibold text-lg">
          <icon-carbon-chevron-mini />
          {{ route.meta.frontmatter.title }}
        </div>
        <div v-if="route.meta.frontmatter.type=='article'" class="mx-8 title font-semibold text-base">
          <icon-carbon-chevron-mini />
          {{ route.meta.frontmatter.title }}
        </div>
      </li>
    </router-link>
  </ul>
</template>
