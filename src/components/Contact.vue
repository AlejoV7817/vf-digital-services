<script setup>
import { onMounted, onUnmounted } from 'vue'

const emit = defineEmits(['close'])

// 🔥 cerrar con ESC
const handleKey = (e) => {
  if (e.key === 'Escape') emit('close')
}

// 🔥 bloquear scroll fondo
onMounted(() => {
  document.body.style.overflow = 'hidden'
  window.addEventListener('keydown', handleKey)
})

onUnmounted(() => {
  document.body.style.overflow = 'auto'
  window.removeEventListener('keydown', handleKey)
})

// 🔥 click fuera
const closeIfOutside = (e) => {
  if (e.target.classList.contains('overlay')) {
    emit('close')
  }
}
</script>

<template>
  <!-- 🔥 OVERLAY -->
  <div class="overlay" @click="closeIfOutside">

    <section class="contact">

      <!-- BOTÓN CERRAR -->
      <button class="close" @click="emit('close')">✕</button>

      <p class="tag">CONTACTO</p>

      <h2>
        Hablemos sobre tu <span>proyecto</span>
      </h2>

      <p class="desc">
        Estamos listos para ayudarte a llevar tu negocio al siguiente nivel.
      </p>

      <!-- GRID -->
      <div class="contact-grid">

        <!-- EMAIL -->
        <a href="mailto:vfdigitalservicess@gmail.com" class="contact-card">
          <i class="fas fa-envelope"></i>
          <h3>Email</h3>
          <p>vfdigitalservicess@gmail.com</p>
        </a>

        <!-- WHATSAPP -->
        <a 
          href="https://wa.me/5215618049841?text=Hola,%20quiero%20información%20sobre%20una%20página%20web"
          target="_blank"
          class="contact-card"
        >
          <i class="fab fa-whatsapp"></i>
          <h3>WhatsApp</h3>
          <p>+52 5618049841</p>
        </a>

        <!-- REDES -->
        <div class="contact-card social">

          <i class="fas fa-share-alt"></i>
          <h3>Redes</h3>

          <div class="social-links">

            <a href="https://www.instagram.com/vf_digital_services" target="_blank">
              <i class="fab fa-instagram"></i>
            </a>

            <a href="https://www.tiktok.com/@vfdigitalservicess" target="_blank">
              <i class="fab fa-tiktok"></i>
            </a>

            <a href="https://wa.me/5215618049841" target="_blank">
              <i class="fab fa-whatsapp"></i>
            </a>

          </div>

        </div>

      </div>

    </section>

  </div>
</template>

<style scoped>

/* 🔥 FONDO OVERLAY */
.overlay {
  position: fixed;
  inset: 0;
  z-index: 2000;

  background: rgba(0,0,0,0.85);
  backdrop-filter: blur(12px);

  display: flex;
  align-items: center;
  justify-content: center;

  animation: fadeIn 0.3s ease;
}

/* CONTENIDO */
.contact {
  width: 90%;
  max-width: 900px;

  padding: 60px 30px;
  border-radius: 20px;

  text-align: center;
  color: white;

  background:
    radial-gradient(circle at 20% 30%, rgba(168,85,247,0.15), transparent),
    radial-gradient(circle at 80% 70%, rgba(59,130,246,0.15), transparent),
    #06060a;

  position: relative;

  animation: scaleIn 0.3s ease;
}

/* BOTÓN CERRAR */
.close {
  position: absolute;
  top: 20px;
  right: 20px;

  background: rgba(255,255,255,0.05);
  border: none;
  color: white;

  width: 40px;
  height: 40px;
  border-radius: 10px;

  font-size: 18px;
  cursor: pointer;

  transition: 0.25s;
}

.close:hover {
  background: linear-gradient(90deg,#a855f7,#3b82f6);
}

/* TITULO */
h2 {
  font-size: 2.4rem;
  margin-bottom: 20px;
}

h2 span {
  background: linear-gradient(90deg,#a855f7,#3b82f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.tag {
  color: #ec4899;
  margin-bottom: 10px;
}

.desc {
  color: #9ca3af;
  margin-bottom: 40px;
}

/* GRID */
.contact-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

/* CARDS */
.contact-card {
  background: rgba(255,255,255,0.02);
  border: 1px solid rgba(255,255,255,0.08);
  padding: 25px;
  border-radius: 14px;
  text-decoration: none;
  color: white;
  transition: 0.3s;
}

.contact-card:hover {
  transform: translateY(-6px);
  border-color: rgba(168,85,247,0.4);
  box-shadow: 0 10px 25px rgba(168,85,247,0.2);
}

/* ICONOS */
.contact-card i {
  font-size: 28px;
  margin-bottom: 12px;

  background: linear-gradient(90deg,#a855f7,#3b82f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* REDES */
.social-links {
  display: flex;
  justify-content: center;
  gap: 12px;
  margin-top: 10px;
}

.social-links a {
  width: 44px;
  height: 44px;
  border-radius: 10px;

  display: flex;
  align-items: center;
  justify-content: center;

  font-size: 18px;

  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);

  transition: 0.25s;
}

.social-links a:hover {
  transform: translateY(-3px);
  background: linear-gradient(90deg,#a855f7,#3b82f6);
}

/* ANIMACIONES */
@keyframes fadeIn {
  from { opacity: 0 }
  to { opacity: 1 }
}

@keyframes scaleIn {
  from {
    opacity: 0;
    transform: scale(0.9);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

/* RESPONSIVE */
@media (max-width: 900px) {
  .contact-grid {
    grid-template-columns: 1fr;
  }
}
</style>