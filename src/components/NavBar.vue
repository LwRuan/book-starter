<template>
  <header class="h-16 p-3 text-2xl font-bold text-gray-700 dark:text-gray-200">
    <nav class="flex flex-row">
      <router-link
        to="/"
        focusable="false"
        class="w-8 h-8"
      >
        <img src="/vcl-logo.png">
      </router-link>
      <div class="flex-grow" />
      <div>
        <router-link
          to="/book"
          focusable="false"
        >
          <icon-carbon-book class="mx-2" />
        </router-link>
        <button class="icon-btn mx-2 !outline-none" :title="t('button.toggle_dark')" @click="toggleDark()">
          <icon-carbon-moon v-if="isDark" />
          <icon-carbon-sun v-else />
        </button>
        <a class="icon-btn mx-2" rel="noreferrer" href="https://github.com/LwRuan/book-starter" target="_blank" title="GitHub">
          <icon-carbon-logo-github />
        </a>
      </div>
    </nav>
  </header>
</template>

<script setup lang="ts">
import { isDark, toggleDark } from '~/logic'
const { t } = useI18n()
</script>
