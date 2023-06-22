<script setup lang="ts">
defineOptions({
  name: 'IndexPage',
})

useHead({
  title: '这个人好奇怪啊 - Misaka-L Index',
})
</script>

<template>
  <div class="index">
    <div class="info-card">
      <h1>总而言之是个很奇怪的人</h1>
      <p>TODO</p>
    </div>
  </div>
</template>

<style scoped>
.index {
  background-image: url("/header.webp");
  background-position: center bottom;
  background-repeat: no-repeat;
  background-size: cover;
  height: 100%;

  display: flex;
  justify-content: center;
  align-items: center;
}

.info-card {
  text-align: center;
}
</style>
