<script setup lang="ts">
import { availableLocales, loadLanguageAsync } from '~/modules/i18n'

const { t, locale } = useI18n()

async function toggleLocales() {
  // change to some real logic
  const locales = availableLocales
  const newLocale = locales[(locales.indexOf(locale.value) + 1) % locales.length]
  await loadLanguageAsync(newLocale)
  locale.value = newLocale
}
</script>

<template>
  <div class="navigation-bar">
    <div class="navigation-icon">
      <img src="/akari.webp">
      <span>Misaka-L Index</span>
    </div>
    <div class="navigation-links">
      <RouterLink to="/">
        {{ t("nav.home") }}
      </RouterLink>
      <RouterLink to="/blog">
        {{ t("nav.blog") }}
      </RouterLink>
      <RouterLink to="/message-books">
        {{ t("nav.message-books") }}
      </RouterLink>
    </div>
    <div class="navigation-icon-links">
      <a icon-btn :title="t('button.toggle_langs')" @click="toggleLocales()">
        <div i-carbon-language />
      </a>
      <button icon-btn :title="t('button.toggle_dark')" @click="toggleDark()">
        <div i="carbon-sun dark:carbon-moon" />
      </button>
      <a icon-btn href="https://github.com/Misaka-L" target="_blank" title="Github">
        <div i-carbon-logo-github />
      </a>
    </div>
  </div>
</template>

<style scoped lang="less">
.navigation-bar {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 0 3rem;
  position: fixed;
  width: 100%;

  backdrop-filter: blur(1rem);
  background-color: rgba(0, 0, 0, 0.308);
  color: white;
}

.navigation-icon {
  display: flex;
  flex: 1;
  flex-direction: row;
  align-items: center;
  padding: 1rem;

  span {
    padding-left: 1rem;
    font-size: 1.2rem;
  }

  img {
    height: 30px;
    border-radius: 1rem;
  }
}

.navigation-links {
  display: flex;
  flex: 1;
  justify-content: right;
  padding-right: 1rem;

  a {
    margin: 0 1rem;
  }
}

.navigation-icon-links {
  display: flex;
  align-items: center;
  font-size: 1.25rem;

  * {
    padding-right: 1rem;
  }
}
</style>
