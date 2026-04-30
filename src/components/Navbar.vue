<script setup>
import { ref } from 'vue'

const open = ref(false)

// 🔥 ahora emite DOS eventos
const emit = defineEmits(['open-contact', 'open-privacy'])

const openContact = () => {
  emit('open-contact')
}

const openPrivacy = () => {
  emit('open-privacy')
}
</script>

<template>
  <header class="nav">
    
    <div class="wrap container-global">

      <!-- MARCA -->
      <div class="brand">
        vf_digital_services
      </div>

      <!-- MENU -->
      <nav class="menu" :class="{ show: open }">
        <a href="#">Inicio</a>
        <a href="#nosotros">Nosotros</a>
        <a href="#servicios">Servicios</a>

        <a href="#" @click.prevent="openContact">Contacto</a>

        <!-- 🔥 NUEVO BOTÓN -->
        <a href="#" class="privacy" @click.prevent="openPrivacy">
          Privacidad
        </a>
      </nav>

      <!-- CTA -->
      <a href="#" @click.prevent="openContact" class="cta">
        Contáctanos
      </a>

      <!-- HAMBURGUESA -->
      <button class="hamb" @click="open = !open">
        ☰
      </button>

    </div>
  </header>
</template>

<style scoped>

/* 🔥 BOTÓN PRIVACIDAD MÁS SUTIL */
.privacy {
  font-size: 0.8rem;
  color: #9ca3af;
  text-decoration: none;
  transition: 0.2s;
}

.privacy:hover {
  color: #a855f7;
}

</style>

<style scoped>
.nav {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;

  background: rgba(6,6,10,0.65);
  backdrop-filter: blur(12px);

  border-bottom: 1px solid rgba(255,255,255,0.06);
}

/* WRAP */
.wrap {
  height: 70px;
  display: grid;
  grid-template-columns: auto 1fr auto auto;
  align-items: center;
  gap: 30px;
}

/* MARCA */
.brand {
  font-size: 1.1rem;
  font-weight: 600;
  letter-spacing: 1px;

  background: linear-gradient(90deg,#ec4899,#a855f7,#3b82f6);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* MENU */
.menu {
  display: flex;
  justify-content: center;
  gap: 28px;
}

.menu a {
  font-size: 0.95rem;
  color: #cfcfd4;
  text-decoration: none;
  font-weight: 500;
  transition: 0.25s;
  position: relative;
}

/* HOVER LINE */
.menu a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -6px;
  width: 0%;
  height: 2px;

  background: linear-gradient(90deg,#a855f7,#3b82f6);
  transition: 0.25s;
}

.menu a:hover {
  color: white;
}

.menu a:hover::after {
  width: 100%;
}

/* BOTON */
.cta {
  font-size: 0.9rem;
  padding: 10px 18px;
  border-radius: 10px;
  text-decoration: none;
  color: white;
  font-weight: 600;

  background: linear-gradient(90deg,#a855f7,#3b82f6);

  transition: 0.25s;
}

.cta:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(168,85,247,0.3);
}

/* HAMB */
.hamb {
  display: none;
  background: none;
  border: none;
  color: white;
  font-size: 1.4rem;
}

/* MOBILE */
@media (max-width: 900px) {
  .menu {
    position: absolute;
    top: 70px;
    right: 20px;

    flex-direction: column;
    width: 220px;

    background: #0a0a0a;
    border-radius: 12px;

    padding: 10px 0;
    display: none;
  }

  .menu.show {
    display: flex;
  }

  .menu a {
    padding: 12px 20px;
  }

  .cta {
    display: none;
  }

  .hamb {
    display: block;
  }
}
</style>