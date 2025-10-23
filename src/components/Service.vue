<script setup>
import Card from 'primevue/card'
import '../styles/service.css'
const services = [
  {
    title: 'Real Estate Done Right',
    image: '/os1.webp',
    description: `Whether you're buying, selling, or investing—we're here to support your property adventure. 
    We believe in making the experience as smooth and empowering as possible.`
  },
  {
    title: 'Commercial & Residential',
    image: '/os2.webp',
    description: `From small condos to luxury estates, fixer-uppers to dream homes—we help you find the right fit. 
    Our team is here to guide your decisions with clarity and care.`
  },
  {
    title: 'Rely on Expertise',
    image: '/os3.webp',
    description: `Affordability, credit, loan options—we connect you with the right people and insights. 
    Make confident, educated choices with expert support at every step.`
  }
]
</script>

<template>
  <section class="services-section">
    <h2>Our Services</h2>
    <div class="services-grid">
      <Card v-for="(service, index) in services" :key="index" class="service-card">
        <template #content>
          <img :src="service.image" :alt="service.title" class="service-img" />
          <h3>{{ service.title }}</h3>
          <p>{{ service.description }}</p>
        </template>
      </Card>
    </div>
  </section>
</template>
