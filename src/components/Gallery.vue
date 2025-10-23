<script setup>
import { ref } from 'vue'
import Carousel from 'primevue/carousel'
import Image from 'primevue/image'
import '../styles/gallery.css'

const images = [
  '/pg1.webp',
  '/pg2.webp',
  '/pg3.webp',
  '/pg4.webp',
  '/pg5.webp',
  '/pg6.webp',
  '/pg7.webp'
]

const activeIndex = ref(0)

const onPageChange = (event) => {
  activeIndex.value = event.page
}
</script>

<template>
  <section class="section section-light">
    <div class="gallery-wrapper">
      <h2>Our Projects</h2>
     <Carousel
  :value="images"
  :numVisible="1"
  :numScroll="1"
  circular
  :autoplayInterval="3000"
  v-model:page="activeIndex"
  @update:page="onPageChange"
  :responsiveOptions="[
    { breakpoint: '1024px', numVisible: 1, numScroll: 1 },
    { breakpoint: '768px', numVisible: 1, numScroll: 1 }
  ]"
  contentClass="carousel-content"
>
  <template #item="{ data }">
    <div class="carousel-slide">
      <img :src="data" alt="Gallery image" class="gallery-img" />
    </div>
  </template>
</Carousel>

      <!-- Custom Indicators -->
      <div class="custom-indicators">
        <span
          v-for="(img, index) in images"
          :key="index"
          class="dot"
          :class="{ active: index === activeIndex }"
          @click="activeIndex = index"
        ></span>
      </div>
    </div>
  </section>
</template>
