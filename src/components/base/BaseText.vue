<script setup>
defineProps({
  tagName: String,
  size: String,
  bold: Boolean
})
</script>

<template>
  <tagName :class="[`text`, `text--${size}`, bold ? `text--bold` : '']">
    <slot></slot>
  </tagName>
</template>

<style scoped lang="scss">
.text {
  font-weight: 500;
  line-height: 1.6;
  color: var(--color-black);

  &--l {
    font-size: 1rem;
  }

  &--m {
    font-size: 0.875rem;
  }

  &--s {
    font-size: 0.75rem;
  }

  &--bold {
    font-weight: 700;
  }
}
</style>
