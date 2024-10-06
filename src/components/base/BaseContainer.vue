<template>
  <div class="container">
    <slot></slot>
  </div>
</template>

<style scope lang="scss">
.container {
  margin: 0 auto;
  padding: 0 var(--container-offset);
  max-width: var(--container-width);
}
</style>
