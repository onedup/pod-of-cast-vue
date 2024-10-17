<script setup>
defineProps({
  tagName: String,
  size: String,
  lineHeight: String,
  bold: Boolean
})
</script>

<template>
  <tagName
    :class="[
      `title`,
      `title--${size}`,
      lineHeight ? `title--lh${lineHeight}` : '',
      bold ? `title--bold` : ''
    ]"
  >
    <slot></slot>
  </tagName>
</template>

<style scoped lang="scss">
.title {
  font-weight: 500;
  color: var(--color-black);

  &--h1 {
    font-weight: 700;
    font-size: 3.6875rem;
    letter-spacing: -0.02em;
  }

  &--h2 {
    font-weight: 700;
    font-size: 2.25rem;
    letter-spacing: -0.02em;
  }

  &--h3 {
    font-weight: 500;
    font-size: 1.375rem;
  }

  &--h3.title--bold {
    letter-spacing: -0.02em;
  }

  &--lh100 {
    line-height: 1;
  }

  &--lh120 {
    line-height: 1.2;
  }

  &--lh140 {
    line-height: 1.4;
  }

  &--lh160 {
    line-height: 1.6;
  }

  &--bold {
    font-weight: 700;
  }
}
</style>
