<script setup>
import { ref } from 'vue'

const current = ref(0)
const showAll = ref(false)

const reviews = [
  { text: "Excelente servicio. Mi página ahora genera clientes todos los días.", name: "Carlos Méndez", role: "Negocio local" },
  { text: "Diseño moderno y profesional. Superaron mis expectativas.", name: "Andrea López", role: "Emprendedora" },
  { text: "Soporte técnico increíble. Todo rápido y eficiente.", name: "Luis Herrera", role: "Empresa" },
  { text: "Aumenté mis ventas gracias a su marketing digital.", name: "Fernando Ruiz", role: "E-commerce" },
  { text: "Muy buena atención y resultados reales.", name: "Daniel Torres", role: "Freelancer" },
  { text: "Mi negocio ahora se ve profesional en internet.", name: "Sofía Ramos", role: "Tienda online" },
  { text: "El SEO funcionó, ahora aparezco en Google.", name: "Ricardo Vega", role: "Servicios" },
  { text: "Muy recomendados, calidad y atención excelente.", name: "Laura Jiménez", role: "Empresa local" }
]

function next() {
  current.value = (current.value + 1) % reviews.length
}

function prev() {
  current.value = (current.value - 1 + reviews.length) % reviews.length
}
</script>

<template>
  <section class="testimonials">

    <div class="container-global">

      <h2>Lo que nuestros clientes dicen</h2>

      <!-- SLIDER -->
      <div class="slider" v-if="!showAll">

        <button class="nav-btn left" @click="prev">‹</button>

        <div class="review">
          <p class="text">“{{ reviews[current].text }}”</p>
          <h3>{{ reviews[current].name }}</h3>
          <span>{{ reviews[current].role }}</span>
        </div>

        <button class="nav-btn right" @click="next">›</button>

      </div>

      <!-- 🔥 GRID DE 8 RESEÑAS -->
      <div v-else class="all-reviews">
        <div class="review-card" v-for="(r, i) in reviews" :key="i">
          <p>“{{ r.text }}”</p>
          <h4>{{ r.name }}</h4>
          <span>{{ r.role }}</span>
        </div>
      </div>

      <!-- BOTONES -->
      <div class="actions">
        <button class="btn" @click="showAll = !showAll">
          {{ showAll ? 'Volver' : 'Ver todos los comentarios' }}
        </button>

    
      </div>

    </div>

  </section>
</template>

<style scoped>
/* 🔥 NUEVO BACKGROUND MÁS PRO */
.testimonials {
  padding: 120px 20px;
  color: white;
  text-align: center;

  background:
    radial-gradient(circle at 20% 30%, rgba(168,85,247,0.15), transparent 50%),
    radial-gradient(circle at 80% 70%, rgba(59,130,246,0.15), transparent 50%),
    #07070b;
}

/* TITULO */
h2 {
  font-size: 2.6rem;
  margin-bottom: 60px;
}

/* SLIDER */
.slider {
  position: relative;
  max-width: 800px;
  margin: auto;
}

/* REVIEW */
.text {
  font-size: 1.3rem;
  color: #d1d5db;
  margin-bottom: 25px;
}

h3 {
  font-size: 1.2rem;
}

span {
  color: #9ca3af;
}

/* BOTONES SLIDER */
.nav-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(255,255,255,0.05);
  border: none;
  color: white;
  font-size: 1.5rem;
  width: 45px;
  height: 45px;
  border-radius: 50%;
  cursor: pointer;
}

.nav-btn:hover {
  background: linear-gradient(90deg,#a855f7,#3b82f6);
}

.left { left: -60px; }
.right { right: -60px; }

/* 🔥 GRID DE RESEÑAS */
.all-reviews {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  max-width: 1100px;
  margin: auto;
}

.review-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.08);
  padding: 20px;
  border-radius: 12px;
  transition: 0.3s;
}

.review-card:hover {
  transform: translateY(-5px);
  border-color: rgba(168,85,247,0.4);
}

/* BOTONES */
.actions {
  margin-top: 60px;
  display: flex;
  justify-content: center;
  gap: 20px;
}

.btn {
  padding: 14px 28px;
  border-radius: 10px;
  border: none;
  background: linear-gradient(90deg,#a855f7,#3b82f6);
  color: white;
  cursor: pointer;
}

.outline {
  background: transparent;
  border: 1px solid #a855f7;
}

/* RESPONSIVE */
@media (max-width: 900px) {
  .all-reviews {
    grid-template-columns: 1fr;
  }

  .nav-btn {
    display: none;
  }
}
</style>