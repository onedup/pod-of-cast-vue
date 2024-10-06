<template>
  <h2 class="title">
    <slot></slot>
    <!-- Основной текст заголовка -->
    <span class="title--highlight"><slot name="title--highlight"></slot></span>
    <!-- Текст с другим цветом -->
  </h2>
</template>

<script setup lang="ts">
// В данном случае никаких дополнительных скриптовых настроек не требуется
</script>

<style scoped lang="scss">
.title {
  font-weight: 700;
  font-size: 6rem;
  line-height: 1;
  letter-spacing: -0.04em;
  text-align: center;
  color: #000;

  &--highlight {
    color: var(--color-vermillion);
  }
}
</style>
