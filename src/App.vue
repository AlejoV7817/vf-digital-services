<script setup>
import { ref } from 'vue'

import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Nosotros from './components/Nosotros.vue'
import Services from './components/Services.vue'
import Testimonials from './components/Testimonials.vue'
import Contact from './components/Contact.vue'
import Privacy from './components/Privacy.vue' // 🔥 NUEVO

// 🔥 CONTACTO
const showContact = ref(false)

const openContact = () => {
  showContact.value = true
}

const closeContact = () => {
  showContact.value = false
}

// 🔥 PRIVACIDAD
const showPrivacy = ref(false)

const openPrivacy = () => {
  showPrivacy.value = true
}

const closePrivacy = () => {
  showPrivacy.value = false
}
</script>

<template>
  <!-- NAVBAR -->
  <Navbar 
    @open-contact="openContact" 
    @open-privacy="openPrivacy" 
  />

  <!-- SECCIONES -->
  <Hero />
  <Nosotros />
  <Services />
  <Testimonials />

  <!-- 🔥 MODALES -->
  <Contact v-if="showContact" @close="closeContact" />
  <Privacy v-if="showPrivacy" @close="closePrivacy" />
</template>

<style>
body {
  margin: 0;
  font-family: 'Inter', sans-serif;
  background: #050507;
}

/* scroll suave */
html {
  scroll-behavior: smooth;
}
</style>