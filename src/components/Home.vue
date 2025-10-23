<template>
  <div class="home">
    <Header />
    <div class="home-page">

      <!-- 🟦 HERO SECTION -->
      <section class="hero-section fade-section">
        <div class="hero-bg">
          <img src="/home.webp" alt="Hero Background" />
        </div>

        <div class="hero-content">
          <h1>Pahrump Realtor</h1>
          <p>MARCI METZGER - THE RIDGE REALTY GROUP</p>

          <!-- 🔍 SEARCH FORM inside PrimeVue Card -->
          <Card class="search-card">
            <template #title>
              <h2 class="search-title">Search Listings</h2>
            </template>

           <template #content>
  <div class="search-grid">
    <div class="field">
      <label class="field-label">Location</label>
      <Dropdown v-model="filters.location" :options="locations" placeholder="Select Location" class="p-input-filled" />
    </div>

    <div class="field">
      <label class="field-label">Type</label>
      <Dropdown v-model="filters.type" :options="types" placeholder="Select Type" class="p-input-filled" />
    </div>

    <div class="field">
      <label class="field-label">Sort By</label>
      <Dropdown v-model="filters.sort" :options="sortOptions" placeholder="Select Option" class="p-input-filled" />
    </div>

    <div class="field">
      <label class="field-label">Bedrooms</label>
      <Dropdown v-model="filters.bedrooms" :options="bedrooms" placeholder="Any Number" class="p-input-filled" />
    </div>

    <div class="field">
      <label class="field-label">Baths</label>
      <Dropdown v-model="filters.baths" :options="baths" placeholder="Any Number" class="p-input-filled" />
    </div>

    <div class="field">
      <label class="field-label">Min Price</label>
      <InputText v-model.number="filters.minPrice" type="number" placeholder="$ Min" class="p-input-filled" />
    </div>

    <div class="field">
      <label class="field-label">Max Price</label>
      <InputText v-model.number="filters.maxPrice" type="number" placeholder="$ Max" class="p-input-filled" />
    </div>

    <div class="field full">
    <Button label="Search Now" class="search-btn p-button-lg" />
    </div>
  </div>
</template>
          </Card>
        </div>
      </section>

      <!-- 🔻 SECTION DIVIDERS & CONTENT -->
     
      <Service class="fade-section" />
     
      <Gallery class="fade-section" />
     
      <Testimonial class="fade-section" />
   
      <Contact class="fade-section" />
       
      <Footer class="fade-section" />
    </div>
  </div>
</template>

<script setup>
import Header from '../components/Header.vue'
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
import { ref } from 'vue'
import '../styles/homepage.css'

// Form state
const filters = ref({
  location: null,
  type: null,
  sort: null,
  bedrooms: null,
  baths: null,
  minPrice: '',
  maxPrice: ''
})

// Dropdown options
const locations = ['Los Angeles', 'San Diego', 'San Francisco', 'Sacramento']
const types = ['House', 'Condo', 'Townhouse']
const sortOptions = ['Newest', 'Oldest', 'Price: Low to High', 'Price: High to Low']
const bedrooms = ['1', '2', '3', '4', '5+']
const baths = ['1', '2', '3', '4+']
</script>