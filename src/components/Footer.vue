<template>
  <footer class="footer-section">
    <div class="footer-content">
      <p class="footer-text">Copyright © 2023 Marci METZGER Homes - All Rights Reserved</p>
      <p class="footer-note">
        This site is protected by reCAPTCHA and the Google Privacy Policy and Terms of Service apply.
      </p>

      <div class="social-icons">
        <Button icon="pi pi-facebook" class="social-btn fb" severity="secondary" rounded @click="open('https://facebook.com')" />
        <Button icon="pi pi-instagram" class="social-btn ig" severity="secondary" rounded @click="open('https://instagram.com')" />
        <Button icon="pi pi-linkedin" class="social-btn li" severity="secondary" rounded @click="open('https://linkedin.com')" />
        <Button icon="pi pi-star" class="social-btn yelp" severity="secondary" rounded @click="open('https://yelp.com')" />
      </div>

    <div class="credibility-strip">
        <img src="/r1.webp" alt="The Ridge Realty Group" class="cred-logo" />
        <img src="/r2.webp" alt="Equal Housing Opportunity" class="cred-logo" />
        <img src="/r3.webp" alt="REALTOR®" class="cred-logo" />
        <img src="/r4.webp" alt="Pahrump Valley Chamber of Commerce" class="cred-logo" />
      </div>
    </div>
  </footer>
</template>


<script setup>
import Button from 'primevue/button'
import '../styles/footer.css'
function open(url) {
  window.open(url, '_blank')
}
</script>