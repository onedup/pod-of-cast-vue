<script setup>
defineProps({
  center: Boolean
})
</script>

<template>
  <h2 :class="[`title`, center ? `centered` : '']">
    <slot></slot>
    <!-- Основной текст заголовка -->
    <span class="title--highlight"><slot name="highlight"></slot></span>
    <!-- Текст с другим цветом -->
  </h2>
</template>

<style scoped lang="scss">
.title {
  margin: 0;
  font-weight: 700;
  font-size: 6rem;
  line-height: 1;
  letter-spacing: -0.04em;
  color: #000;
  max-width: 33.75rem;

  &--highlight {
    color: var(--color-vermillion);
  }
}
</style>
