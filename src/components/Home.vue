<template>
   <Header  />
  <div id ="home" class="home">
   
    <div class="home-page">
      <!-- 🟦 HERO SECTION -->
      <section class="landing-page-hero fade-section">
        <div class="landing-page-background">
          <div class="landing-page-overlay">
            <div class="landing-page-content">
              <h1>Pahrump Realtor</h1>
              <p>MARCI METZGER – THE RIDGE REALTY GROUP</p>
            </div>
          </div>
        </div>
      </section>

      <!-- 🔻 SECTION DIVIDERS & CONTENT -->
      <FormPage class="fade-section" />
      <Service id="services" class="fade-section" />
      <Gallery id="gallery" class="fade-section" />
      <Testimonial id="testimonials" class="fade-section" />
      <Contact id="contact" class="fade-section" />
      <Footer class="fade-section" />
    </div>
  </div>
</template>

<script setup>
import Hero from '../components/HeroSection.vue'
import Header from '../components/Header.vue'
import FormPage from './FormPage.vue'
import Service from '../components/Service.vue'
import Gallery from '../components/Gallery.vue'
import Testimonial from '../components/Testimonial.vue'
import Contact from '../components/Contact.vue'
import Footer from '../components/Footer.vue'

import Divider from 'primevue/divider'
import Dropdown from 'primevue/dropdown'
import InputText from 'primevue/inputtext'
import Button from 'primevue/button'
import Card from 'primevue/card'

import { ref, onMounted, onBeforeUnmount } from 'vue'
import '../styles/homepage.css'
import '../styles/animation.css'
import '../styles/landingpage.css'

// Form state (used in FormPage)
const filters = ref({
  location: null,
  type: null,
  sort: null,
  bedrooms: null,
  baths: null,
  minPrice: '',
  maxPrice: ''
})

const locations = ['Los Angeles', 'San Diego', 'San Francisco', 'Sacramento']
const types = ['House', 'Condo', 'Townhouse']
const sortOptions = ['Newest', 'Oldest', 'Price: Low to High', 'Price: High to Low']
const bedrooms = ['1', '2', '3', '4', '5+']
const baths = ['1', '2', '3', '4+']

let observer

onMounted(() => {
  observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      entry.target.classList.toggle('visible', entry.isIntersecting)
    })
  }, { threshold: 0.2 })

  const fadeSections = document.querySelectorAll('.fade-section')
  fadeSections.forEach(section => observer.observe(section))
})

onBeforeUnmount(() => {
  const fadeSections = document.querySelectorAll('.fade-section')
  fadeSections.forEach(section => observer.unobserve(section))
})
</script>