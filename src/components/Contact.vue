<script setup>
import InputText from 'primevue/inputtext'
import Textarea from 'primevue/textarea'
import Button from 'primevue/button'
import Card from 'primevue/card'
import '../styles/contact.css'

const contactInfo = {
  name: 'Marci Metzger - THE RIDGE REALTY GROUP',
  address: '2310 W 4900 Rd, Suite F, Pahrump, Nevada 89048, United States',
  phone: '(206) 619-4866',
  hours: [
    'Tuesday only: 10:00 am – 11:00 pm',
    'Open daily: 8:00 am – 7:00 pm',
    'Appointments outside office hours available upon request'
  ]
}
</script>

<template>
  <section class="contact-section">
    <h2>Contact Us</h2>

   

    <!-- Contact Grid -->
    <div class="contact-grid">
      <!-- Contact Form -->
      <Card class="contact-card">
        <template #content>
          <form class="contact-form">
            <label for="name">Name</label>
            <InputText id="name" class="contact-input" />

            <label for="email">Email</label>
            <InputText id="email" class="contact-input" />

            <label for="message">Message</label>
            <Textarea id="message" rows="5" class="contact-textarea" />

            <Button label="SEND" severity="primary" class="send-btn" />
            <Button label="Message us on WhatsApp" severity="success" class="whatsapp-btn" icon="pi pi-whatsapp" />
          </form>
        </template>
      </Card>

      <!-- Office Info -->
      <Card class="contact-card">
        <template #content>
          <div class="office-info">
            <img src="/marcimetzger.webp" alt="Agent Photo" class="agent-img" />
            <h3>{{ contactInfo.name }}</h3>
            <p>{{ contactInfo.address }}</p>
            <p><strong>Phone:</strong> {{ contactInfo.phone }}</p>
            <ul>
              <li v-for="(line, index) in contactInfo.hours" :key="index">{{ line }}</li>
            </ul>
            <p class="disclaimer">
              This site is protected by reCAPTCHA and the Google Privacy Policy and Terms of Service apply.
            </p>
          </div>
        </template>
      </Card>
    </div>

     <!-- Map Card -->
    <Card class="map-card">
      <template #content>
        <div class="contact-map">
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d103027.5150192818!2d-116.05601277945905!3d36.200369409982976!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x80c639760f7b12f3%3A0xa05207dd285dc73c!2sTHE%20RIDGE%20REALTY%20GROUP!5e0!3m2!1sen!2sph!4v1761148801044!5m2!1sen!2sph"
            width="100%"
            height="300"
            style="border:0;"
            allowfullscreen
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"
          ></iframe>
        </div>
      </template>
    </Card>
  </section>
</template>