<script setup>
import BaseContainer from '@/components/base/BaseContainer.vue'
import BaseDisplayTitle from '@/components/base/BaseDisplayTitle.vue'
import BaseText from '@/components/base/BaseText.vue'
import BaseButton from '@/components/base/BaseButton.vue'
import BasePodcastCard from '@/components/base/BasePodcastCard.vue'
import BaseSupportedBy from '@/components/base/BaseSupportedBy.vue'
import IconSpiralWickDecor from '@/components/icons/IconSpiralWickDecor.vue'
import IconStarsDecor from '@/components/icons/IconStarsDecor.vue'
import { AutoScroll } from '@splidejs/splide-extension-auto-scroll'

const splideOptions = {
  gap: '1.25rem',
  autoWidth: true,
  type: 'loop',
  focus: 'center',
  autoScroll: {
    speed: 1
  },
  pagination: false,
  arrows: false
}
</script>

<template>
  <section class="hero">
    <BaseContainer class="hero__container">
      <BaseDisplayTitle class="hero__display-title centered"
        >Your Daily <template v-slot:highlight>Podcast</template></BaseDisplayTitle
      >
      <BaseText class="hero__text centered" :tag-name="p" size="l"
        >We cover all kinds of categories and a weekly special guest.</BaseText
      >
      <BaseButton class="hero__btn" size="l">SUBSCRIBE</BaseButton>
      <Splide :options="splideOptions" :extensions="{ AutoScroll }" class="hero__slider">
        <SplideSlide
          ><BasePodcastCard
            size="m"
            :background-image="'src/assets/images/shows/tesla-autopilot.jpg'"
            >Tesla Autopilot</BasePodcastCard
          ></SplideSlide
        >
        <SplideSlide
          ><BasePodcastCard
            size="m"
            :background-image="'src/assets/images/shows/self-confidence.jpg'"
            >Self–confidence</BasePodcastCard
          ></SplideSlide
        >
        <SplideSlide
          ><BasePodcastCard
            size="m"
            :background-image="'src/assets/images/shows/perplexed-mind.jpg'"
            >Perplexed Mind</BasePodcastCard
          ></SplideSlide
        >
        <SplideSlide
          ><BasePodcastCard size="m" :background-image="'src/assets/images/shows/womens-rights.jpg'"
            >Women’s Rights</BasePodcastCard
          ></SplideSlide
        >
        <SplideSlide
          ><BasePodcastCard size="m" :background-image="'src/assets/images/shows/social-class.jpg'"
            >Social Class</BasePodcastCard
          ></SplideSlide
        >
      </Splide>
      <BaseSupportedBy class="hero__supported" />
      <IconSpiralWickDecor class="hero__decor1" :is-animation="true" />
      <IconStarsDecor class="hero__decor2" :is-animation="true" />
    </BaseContainer>
  </section>
</template>

<style scoped lang="scss">
.hero {
  background-color: var(--champagne);
  overflow: hidden;

  &__container {
    position: relative;
    z-index: 1;

    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &__display-title {
    padding-top: 2rem;
    margin-bottom: 1.625rem;
    max-width: 33.75rem;
  }

  &__text {
    margin-bottom: 60px;
    max-width: 18.75rem;
  }

  &__btn {
    margin-bottom: 7.5rem;
  }

  &__slider {
    margin-bottom: 7.5rem;
  }

  &__supported {
    margin-bottom: 8.5rem;
  }

  &__decor1 {
    position: absolute;
    top: -60px;
    left: -428px;
  }
  &__decor2 {
    position: absolute;
    top: 105px;
    right: -64px;
  }
}
</style>
