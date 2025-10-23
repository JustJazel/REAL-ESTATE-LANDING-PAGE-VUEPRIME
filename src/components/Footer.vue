<template>
  <footer class="footer-section">
    <div class="footer-content">
      <p class="footer-note">Copyright © 2023 Marci METZGER Homes – All Rights Reserved</p>
      <p class="footer-note">
        This site is protected by reCAPTCHA and the Google Privacy Policy and Terms of Service apply.
      </p>

      <div class="social-icons">
        <Button class="social-btn fb" severity="secondary" rounded @click="open('https://www.facebook.com/MarciHomes/')" v-tooltip.top="'Facebook'">
          <img src="/facebook.png" alt="Facebook" class="social-icon" />
        </Button>

        <Button class="social-btn ig" severity="secondary" rounded @click="open('https://www.instagram.com/marciandlauren_nvrealtors/')" v-tooltip.top="'Instagram'">
          <img src="/instagram.png" alt="Instagram" class="social-icon" />
        </Button>

        <Button class="social-btn li" severity="secondary" rounded @click="open('https://www.linkedin.com/in/marci-metzger-30642496/')" v-tooltip.top="'LinkedIn'">
          <img src="/linkedin.png" alt="LinkedIn" class="social-icon" />
        </Button>

        <Button class="social-btn yelp" severity="secondary" rounded @click="open('https://www.yelp.com/biz/marci-metzger-the-ridge-realty-pahrump')" v-tooltip.top="'Yelp'">
          <img src="/yelp.png" alt="Yelp" class="social-icon" />
        </Button>
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