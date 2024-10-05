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
  color: var(--title-color, #000); // Основной цвет текста

  &--highlight {
    color: var(--highlight-color, #ff4500); // Цвет для выделенного текста
  }
}
</style>
