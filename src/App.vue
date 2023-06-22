<script setup lang="ts">
// https://github.com/vueuse/head
// you can use this to manipulate the document head in any components,
// they will be rendered correctly in the html results with vite-ssg
useHead({
  title: 'Misaka-L Index',
  meta: [
    { name: 'description', content: '一个奇怪的人' },
    {
      name: 'theme-color',
      content: () => isDark.value ? '#00aba9' : '#ffffff',
    },
  ],
  link: [
    { rel: 'apple-touch-icon', sizes: '180x180', href: '/apple-touch-icon.png' },
    { rel: 'icon', type: 'image/png', sizes: '32x32', href: '/pwa-32x32.png' },
    { rel: 'icon', type: 'image/png', sizes: '16x16', href: '/pwa-16x16.png' },
    { rel: 'icon', type: 'image/png', sizes: '192x192', href: '/pwa-192x192.png' },
    { rel: 'icon', type: 'image/png', sizes: '512x512', href: '/pwa-512x512.png' },
    { rel: 'manifest', href: 'site.webmanifest' },
  ],
})
</script>

<template>
  <NavigationBar />
  <RouterView />
</template>
