<script setup>
import BaseText from '@/components/base/BaseText.vue'
defineProps({
  navLinks: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <nav class="nav">
    <ul class="list-reset nav__list">
      <li v-for="link in navLinks" :key="link.url" class="nav__item">
        <BaseText
          tag-name="a"
          size="l"
          bold
          :href="link.url"
          :class="['nav__link', link.subLinks.length ? 'nav__link--drop' : '']"
          >{{ link.name }}</BaseText
        >
        <ul
          v-if="link.subLinks.length"
          class="list-reset nav__list nav__list--dropdown dropdown-list"
        >
          <li v-for="subLink in link.subLinks" :key="subLink.url" class="dropdown-list__item">
            <BaseText tag-name="a" size="l" bold :href="subLink.url" class="dropdown-list__link">{{
              subLink.name
            }}</BaseText>
          </li>
        </ul>
      </li>
    </ul>
  </nav>
</template>

<style lang="scss" scope>
.nav {
  &__list {
    display: flex;
    align-items: center;
    gap: 3.75rem;

    &--dropdown {
      position: absolute;
      background-color: #fff;
      z-index: 1;
      right: 0;
      top: 100%;
      padding: 1rem;
      display: block;
      box-shadow: 0 5px 10px 0 rgba(0, 0, 0, 0.2);
      transition: all 0.3s;
      opacity: 0;
      visibility: hidden;
    }
  }

  &__item {
    position: relative;

    &:hover {
      .nav__list--dropdown {
        visibility: visible;
        opacity: 1;
        transition:
          var(--transition-time) visibility ease,
          var(--transition-time) opacity ease;
      }
      .nav__link--drop::after {
        transform: rotate(180deg);
      }
    }
  }

  &__link {
    position: relative;
    color: inherit;

    &:hover::before {
      transition: width 0.2s ease;
      width: 100%;
    }

    &::before {
      content: '';
      position: absolute;
      bottom: -4px;
      left: 0;
      width: 0;
      height: 3px;
      border-radius: 4px;
      background-color: currentColor;
      transition: width 0.2s ease;
    }

    &--drop {
      &::before {
        background-color: transparent;
      }

      &::after {
        content: '';
        display: inline-block;
        margin-left: 4px;
        background-image: url('@/assets/images/arrow-down.svg');
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        width: 1rem;
        height: 1rem;
        transition: var(--transition-time) transform ease;
      }
    }
  }
}

.dropdown-list {
  border-radius: 5px;
  background-color: #fcf8f6;
  &__item:not(:last-child) {
    margin-bottom: 10px;
  }

  &__link {
    color: currentColor;
  }
}
</style>
