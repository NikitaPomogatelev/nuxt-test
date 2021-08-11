<template>
  <div class="about__slider">
    <div v-swiper:mySwiper="swiperOption">
      <div class="swiper-wrapper">
        <div class="swiper-slide" :key="banner" v-for="banner in banners">
          <img :src="banner" />
        </div>
      </div>
    </div>
    <button type="button" class="about-button-prev" slot="button-prev"></button>
    <button type="button" class="about-button-next" slot="button-next"></button>
  </div>
</template>

<script>
import { Swiper, SwiperSlide, directive, slideTo } from 'vue-awesome-swiper'
import Slider from '@/components/Slider.vue'
export default {
  components: {
    Swiper,
    SwiperSlide,
    Slider,
  },
  directives: {
    swiper: directive,
  },
  data() {
    return {
      banners: [
        '/nuxt-test/dist/about-1.jpg',
        '/nuxt-test/dist/about-2.jpg',
        '/nuxt-test/dist/about-3.jpg',
        '/nuxt-test/dist/about-1.jpg',
        '/nuxt-test/dist/about-2.jpg',
        '/nuxt-test/dist/about-3.jpg',
      ],
      swiperOption: {
        slidesPerView: 3,
        spaceBetween: 25,
        loop: true,
        navigation: {
          nextEl: '.about-button-next',
          prevEl: '.about-button-prev',
        },
        breakpoints: {
          1024: {
            slidesPerView: 3,
            spaceBetween: 30,
          },
          769: {
            slidesPerView: 2,
            spaceBetween: 20,
          },
          0: {
            slidesPerView: 1,
            spaceBetween: 10,
          },
        },
      },
    }
  },
  mounted() {
    console.log('Current Swiper instance object', this.mySwiper)
    this.mySwiper.slideTo(3, 1000, false)
  },
}
</script>

<style lang="scss" scoped></style>
