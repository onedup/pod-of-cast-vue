<script setup>
import BaseButton from '@/components/base/MyButton.vue'
import HeaderNav from '@/components/base/HeaderNav.vue'

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
    <div class="container header__container">
      <RouterLink to="/">
        <img src="@/assets/images/logo.svg" alt="logo" />
      </RouterLink>
      <HeaderNav :nav-links="navLinks" />
      <div class="header__btns">
        <BaseButton text="RECENT EPISODES" size="m" variant="stroke" :is-shadow="false" />
        <BaseButton text="subscribe" size="m" variant="fill" />
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
.header {
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
