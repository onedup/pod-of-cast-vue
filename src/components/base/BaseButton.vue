<script setup>
defineProps({
  size: {
    type: String,
    default: 'm'
  },
  variant: {
    type: String,
    default: 'fill'
  },
  isShadow: {
    type: Boolean,
    default: true
  }
})
</script>

<template>
  <button
    :class="['btn-reset', 'btn', `btn--${size}`, `btn--${variant}`, isShadow ? `btn--shadow` : '']"
    @click="handleClick"
  >
    <slot></slot>
  </button>
</template>

<style lang="scss" scoped>
.btn {
  border-radius: 0.5rem;
  font-family: var(--font-family);
  font-weight: 700;
  font-size: 0.875rem;
  text-transform: uppercase;

  &--m {
    padding: 0.75rem 1.5rem;
  }

  &--l {
    padding: 1.5rem 3rem;
  }

  &--fill {
    background-color: var(--color-black);
    color: var(--color-white);

    @media (any-hover: hover) {
      &:hover {
        color: var(--pewter-blue);
      }
    }
  }

  &--stroke {
    border: var(--btn-border-width) solid #000;
    background-color: transparent;
    color: var(--color-black);
    transition:
      color var(--transition-time) ease,
      box-shadow var(--transition-time) ease;

    &:active:not(.btn--shadow) {
      border-color: transparent;
      box-shadow: inset 0.09375rem 0.09375rem 0.09375rem 0.09375rem rgba(0, 0, 0, 0.25);
      // color: var(--color-white);
      transform: translate(0.09375rem, 0.09375rem);
      // Move down and shrink slightly
    }

    // Adjust padding to compensate for the added border
    &.btn--m {
      padding: calc(0.75rem - var(--btn-border-width)) calc(1.5rem - var(--btn-border-width));
    }

    &.btn--l {
      padding: calc(1.5rem - var(--btn-border-width)) calc(3rem - var(--btn-border-width));
    }
  }

  &--shadow {
    box-shadow: 0.1875rem 0.1875rem 0 0 rgba(0, 0, 0, 0.25);
    transition:
      var(--transition-time) color,
      0.05s transform,
      0.05s box-shadow;

    &:active {
      transform: translate(0.09375rem, 0.09375rem);
      box-shadow: 0.09375rem 0.09375rem 0 0 rgba(0, 0, 0, 0.25);
    }
  }
}
</style>
