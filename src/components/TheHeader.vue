<script setup>
import BaseContainer from '@/components/base/BaseContainer.vue'
import BaseButton from '@/components/base/BaseButton.vue'
import BaseNav from '@/components/base/BaseNav.vue'

const navLinks = [
  {
    name: 'Episodes',
    url: '/episodes',
    subLinks: []
  },
  {
    name: 'About',
    url: '/about',
    subLinks: []
  },
  {
    name: 'More',
    url: '',
    subLinks: [{ name: 'Blog', url: '/blog' }]
  }
]
</script>

<template>
  <header class="header">
    <BaseContainer class="header__container">
      <RouterLink to="/">
        <img src="@/assets/images/logo.svg" alt="logo" />
      </RouterLink>
      <BaseNav :nav-links="navLinks" />
      <div class="header__btns">
        <BaseButton size="m" variant="stroke" :is-shadow="false">RECENT EPISODES</BaseButton>
        <BaseButton size="m" variant="fill">subscribe</BaseButton>
      </div>
    </BaseContainer>
  </header>
</template>

<style lang="scss" scoped>
.header {
  padding: 24px 0;
  &__container {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  &__btns {
    display: flex;
    gap: 1.25rem;
  }
}
</style>
