<template>
  <section class="about" id="about" ref="about">
    <div class="container about__container">
      <div class="about-row">
        <h2 class="title about__title">О нас</h2>
        <p class="about__descr">
          Сайт рыбатекст поможет дизайнеру, верстальщику, вебмастеру
          сгенерировать несколько абзацев более менее осмысленного текста рыбы
          на&nbsp;русском языке, а&nbsp;начинающему оратору отточить навык
          публичных выступлений в&nbsp;домашних условиях.
        </p>
      </div>
      <a href="#" class="btn about__btn">стать волонтером</a>

      <Slider />

      <ul class="about__list">
        <li class="about__item" v-for="(social, i) in socials" :key="i">
          <a :href="social.href" target="_blank">
            <img :src="social.icon" :alt="social.alt" />
          </a>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
import Slider from '@/components/Slider.vue'
export default {
  components: {
    Slider,
  },
  data() {
    return {
      socials: [
        {
          href: 'https://vk.com/',
          icon: 'vkontakte.svg',
          alt: 'vkontakte',
        },
        {
          href: 'https://www.instagram.com/',
          icon: 'instagram.svg',
          alt: 'instagram',
        },
        {
          href: 'https://ru-ru.facebook.com/',
          icon: 'facebook.svg',
          alt: 'facebook',
        },
        {
          href: 'https://www.youtube.com/',
          icon: 'youtube.svg',
          alt: 'youtube',
        },
      ],
    }
  },
}
</script>

<style></style>
