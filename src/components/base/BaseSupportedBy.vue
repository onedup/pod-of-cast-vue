<script setup>
import IconGooglePodcast from '@/components/icons/IconGooglePodcast.vue'
import IconSpotify from '@/components/icons/IconSpotify.vue'
import IconYouTube from '@/components/icons/IconYouTube.vue'
import BaseTitle from '@/components/base/BaseTitle.vue'
</script>

<template>
  <div class="supported-by">
    <BaseTitle tagName="span" size="h3" line-height="140" bold>Supported by:</BaseTitle>
    <IconSpotify size="l" />
    <IconGooglePodcast size="l" />
    <IconYouTube size="l" />
  </div>
</template>

<style scoped lang="scss">
.supported-by {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  padding: 2.75rem 4.6875rem 2.75rem 0;
  border-top: 0.125rem solid var(--davys-grey);
  border-bottom: 0.125rem solid var(--davys-grey);
  width: 100%;
}
</style>
