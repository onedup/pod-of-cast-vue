<template>
  <h1 class="display-title">
    <slot></slot>
    <!-- Основной текст заголовка -->
    <span class="display-title--highlight"><slot name="highlight"></slot></span>
    <!-- Текст с другим цветом -->
  </h1>
</template>

<style scoped lang="scss">
.display-title {
  margin: 0;
  font-weight: 700;
  font-size: 6rem;
  line-height: 1;
  letter-spacing: -0.04em;
  color: #000;

  &--highlight {
    color: var(--color-vermillion);
  }
}
</style>
