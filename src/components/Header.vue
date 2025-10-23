<template>
  <header class="modern-header">
    <div class="header-inner">
      <img src="/logomarci.webp" alt="Marci Metzger logo" class="logo" id="home"  />
      <nav class="nav">
        <a href="#services">Services</a>
        <a href="#gallery">Gallery</a>
        <a href="#testimonials">Testimonials</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>
</template>

<style>

</style>

<script>
import '../styles/header.css'

export default {
  mounted() {
    const header = document.querySelector('.modern-header');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 50) {
        header.classList.add('scrolled');
      } else {
        header.classList.remove('scrolled');
      }
    });
  }
}
</script>
