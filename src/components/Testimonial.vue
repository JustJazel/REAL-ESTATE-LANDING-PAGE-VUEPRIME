<script setup>
import Card from 'primevue/card'
import '../styles/testimonial.css'

const testimonials = [
  {
    name: 'Top Residential Sales Last 5 Years',
    image: '/gis1.webp',
    quote: `We helped nearly 90 clients in 2021, and closed 28.5 million in sales! 

Our team works hard everyday to grow and learn, so that we may continue to excel in our market. Our clients deserve our best, & we want to make sure our best is better every year.`,
 
  },
  {
    name: 'Do not just list it',
    image: '/gis2.webp',
    quote: `Get it SOLD! We exhaust every avenue to ensure our listings are at the fingertips of every possible buyer, getting you top dollar for your home.`,
  },
  {
    name: 'Guide to Buyers',
    image: '/gis3.webp',
    quote: `Nobody knows the market like we do. Enjoy having a pro at your service. Market analysis, upgrades lists, contractors on speed dial, & more!`,
  }
]
</script>

<template>
  <section class="testimonial-section">
    <h2>Precision in Every Sale</h2>
    <div class="testimonial-grid">
      <Card v-for="(testimonial, index) in testimonials" :key="index" class="testimonial-card">
        <template #content>
          <img :src="testimonial.image" :alt="testimonial.name" class="testimonial-img" />
          <h3>{{ testimonial.name }}</h3>
          <p class="testimonial-role">{{ testimonial.role }}</p>
          <p class="testimonial-quote">“{{ testimonial.quote }}”</p>
        </template>
      </Card>
    </div>
  </section>
</template>