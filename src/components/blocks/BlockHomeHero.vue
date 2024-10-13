<script setup>
import BaseDisplayTitle from '@/components/base/BaseDisplayTitle.vue'
</script>

<template>
  <section class="hero">
    <BaseDisplayTitle class="hero__display-title centered"
      >Your Daily <template v-slot:highlight>Podcast</template></BaseDisplayTitle
    >
  </section>
</template>

<style scoped lang="scss">
.hero {
  background-color: var(--champagne);

  &__display-title {
    margin: 0 auto;
    padding-top: 2.5rem;
    margin-bottom: 2.5rem;
    max-width: 33.75rem;
  }
}
</style>
