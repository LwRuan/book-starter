<template>
  <div class="fixed left-0 right-0">
    <NavBar />
  </div>
  <div class="no-scrollbar border dark:text-gray-200 fixed left-4 w-70 overflow-y-scroll top-16 bottom-4">
    <SideBar />
  </div>
  <body class="fixed left-80 right-0 top-16 bottom-0 overflow-y-scroll text-center text-gray-700 dark:text-gray-200">
    <router-view />
  </body>
</template>

<style scoped>
/* Chrome, Safari and Opera */
.no-scrollbar::-webkit-scrollbar {
  display: none;
}

.no-scrollbar {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;  /* Firefox */
}
</style>
