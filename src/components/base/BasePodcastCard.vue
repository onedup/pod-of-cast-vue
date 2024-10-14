<script setup>
import BaseSpotifyIcon from '@/components/base/BaseSpotifyIcon.vue'
import BaseGooglePodcastIcon from '@/components/base/BaseGooglePodcastIcon.vue'
import BaseYouTubeIcon from '@/components/base/BaseYouTubeIcon.vue'
defineProps({
  shadow: Boolean,
  size: {
    type: String,
    Required: true
  },
  backgroundImage: {
    type: String,
    Required: true
  }
})
</script>

<template>
  <div
    :class="['podcast-card', `podcast-card--${size}  `, shadow ? 'podcast-card--shadow' : '']"
    :style="{ backgroundImage: `url(${backgroundImage})` }"
  >
    <div class="podcast-card__icons">
      <ul class="list-reset podcast-card__icons-list">
        <li class="podcast-card__icons-item">
          <BaseGooglePodcastIcon size="s" />
        </li>
        <li class="podcast-card__icons-item">
          <BaseSpotifyIcon size="s" />
        </li>
        <li class="podcast-card__icons-item">
          <BaseYouTubeIcon size="s" />
        </li>
      </ul>
    </div>
    <span class="podcast-card__title"><slot></slot></span>
  </div>
</template>

<style scoped lang="scss">
.podcast-card {
  padding: 1.25rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  overflow: hidden;

  &--l {
    border-radius: 8px;
    width: 472px;
    height: 472px;
  }

  &--m {
    border-radius: 12px;
    width: 373px;
    height: 373px;
  }

  &--s {
    border-radius: 8px;
    width: 166px;
    height: 166px;
  }

  &__icons {
    align-self: end;
    &-list {
      display: flex;
      gap: 0.625rem;
    }
  }

  &__title {
    font-weight: 700;
    font-size: 36px;
    line-height: 140%;
    letter-spacing: -0.08em;
    color: var(--pewter-blue);
  }

  &--shadow {
    box-shadow: 12px 12px 0 0 var(--pewter-blue);
  }
}
</style>
