<script setup>
import BaseContainer from '@/components/base/BaseContainer.vue'
import BaseDisplayTitle from '@/components/base/BaseDisplayTitle.vue'
import BaseText from '@/components/base/BaseText.vue'
import BaseButton from '@/components/base/BaseButton.vue'
import BasePodcastCard from '@/components/base/BasePodcastCard.vue'

const splideOptions = {
  gap: 20,
  autoWidth: true,
  type: 'loop',
  focus: 'center',
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
      <BaseText class="hero__text centered" tagName="p" size="l"
        >We cover all kinds of categories and a weekly special guest.</BaseText
      >
      <BaseButton class="hero__btn" size="l">SUBSCRIBE</BaseButton>
    </BaseContainer>
    <Splide :options="splideOptions">
      <SplideSlide
        ><BasePodcastCard size="m" backgroundImage="src/assets/images/cover.jpg"
          >Perplexed Mind</BasePodcastCard
        ></SplideSlide
      >
      <SplideSlide
        ><BasePodcastCard size="m" backgroundImage="src/assets/images/cover.jpg"
          >Perplexed Mind</BasePodcastCard
        ></SplideSlide
      >
      <SplideSlide
        ><BasePodcastCard size="m" backgroundImage="src/assets/images/cover.jpg"
          >Perplexed Mind</BasePodcastCard
        ></SplideSlide
      >
      <SplideSlide
        ><BasePodcastCard size="m" backgroundImage="src/assets/images/cover.jpg"
          >Perplexed Mind</BasePodcastCard
        ></SplideSlide
      >
      <SplideSlide
        ><BasePodcastCard size="m" backgroundImage="src/assets/images/cover.jpg"
          >Perplexed Mind</BasePodcastCard
        ></SplideSlide
      >
      <SplideSlide
        ><BasePodcastCard size="m" backgroundImage="src/assets/images/cover.jpg"
          >Perplexed Mind</BasePodcastCard
        ></SplideSlide
      >
    </Splide>
  </section>
</template>

<style scoped lang="scss">
.hero {
  background-color: var(--champagne);

  &__container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &__display-title {
    padding-top: 2.5rem;
    margin-bottom: 2.5rem;
    max-width: 33.75rem;
  }

  &__text {
    margin-bottom: 60px;
    max-width: 18.75rem;
  }

  &__btn {
    margin-bottom: 9rem;
  }
}
</style>
