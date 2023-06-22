<script setup lang="ts">
const { t } = useI18n()
</script>

<template>
  <div class="not-found">
    {{ t('not-found') }}
  </div>
</template>

<style scoped>
.not-found {
  height: 100%;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
}
</style>
