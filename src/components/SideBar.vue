<template>
  <ul class="p-4 grid">
    <li v-for="title in toc">
      <button v-if="(title.i!=0) && (title.lvl<4)" @click="navigate(title.content)">
          <div v-if="title.lvl==1" class="text-xl font-bold">
            {{ title.content }}
          </div>
          <div v-if="title.lvl==2" class="px-2 text-xl">
            {{ title.content }}
          </div>
          <div v-if="title.lvl==3" class="px-4 text-xl">
            {{ title.content }}
          </div>
      </button>
    </li>
  </ul>
</template>

<script lang="ts">
import uslug from 'uslug'
export default {
  data: function () {
  return {
      toc: this.$route.meta.toc,
      current_path: this.$route.path
    }
  },
  methods: {
    navigate: function(s:string){
      const el = document.querySelector("[id=\'" + uslug(s) + "\']");
      console.log(el)
      if (el) {
        el.scrollIntoView();
      }
    }
  },
  watch: {
    '$route.path' (to, from) {
      console.log(this.$route.meta.toc)
      this.$data.toc = this.$route.meta.toc
      this.$data.current_path = this.$route.path
    },
  },
}
</script>
