<script setup>
import { ref } from 'vue'

const current = ref(0)
const showAll = ref(false)
const animate = ref(true)

const reviews = [
  { text: 'Aprendi desde el uso correcto de herramientas hasta cortes completos para dama y caballero.', name: 'Alumna Eskareth', role: 'Curso de estilismo' },
  { text: 'Las clases practicas me ayudaron a ganar seguridad para atender clientes reales.', name: 'Egresada', role: 'Belleza profesional' },
  { text: 'El temario esta completo: corte, peinado, textura, secadora, plancha y tratamientos.', name: 'Estudiante', role: 'Modulo I y II' },
  { text: 'La constancia oficial le da mas valor a mi preparacion y a mi crecimiento profesional.', name: 'Egresada', role: 'Constancia SEP' },
  { text: 'Me gusto que el curso sea para dama, caballero y nino, porque puedo ofrecer mas servicios.', name: 'Alumna', role: 'Estilismo integral' },
  { text: 'Los horarios son accesibles y el proceso de aprendizaje es claro desde el primer modulo.', name: 'Estudiante', role: 'Horario 4 PM a 7 PM' },
  { text: 'Practicar con tijeras, maquina, navaja y secadora hizo que entendiera mejor cada tecnica.', name: 'Alumno', role: 'Practica profesional' },
  { text: 'Eskareth me dio bases para comenzar a emprender dentro del mundo de la belleza.', name: 'Egresada', role: 'Aprende y emprende' },
]

function next() {
  animate.value = false
  setTimeout(() => {
    current.value = (current.value + 1) % reviews.length
    animate.value = true
  }, 150)
}

function prev() {
  animate.value = false
  setTimeout(() => {
    current.value = (current.value - 1 + reviews.length) % reviews.length
    animate.value = true
  }, 150)
}
</script>

<template>
  <section class="testimonials">
    <div class="container-global">
      <h2 class="fade">Lo que puedes lograr en Eskareth</h2>

      <div class="slider" v-if="!showAll">
        <button class="nav-btn left" @click="prev">‹</button>

        <div :class="['review-box', animate ? 'fade' : '']">
          <p class="text">"{{ reviews[current].text }}"</p>
          <h3>{{ reviews[current].name }}</h3>
          <span>{{ reviews[current].role }}</span>
        </div>

        <button class="nav-btn right" @click="next">›</button>
      </div>

      <div v-else class="all-reviews fade">
        <div class="review-card" v-for="(r, i) in reviews" :key="i">
          <p>"{{ r.text }}"</p>
          <h4>{{ r.name }}</h4>
          <span>{{ r.role }}</span>
        </div>
      </div>

      <div class="actions center">
        <button class="btn" @click="showAll = !showAll">
          {{ showAll ? 'Volver' : 'Ver mas aprendizajes' }}
        </button>
      </div>
    </div>
  </section>
</template>

<style>
.testimonials {
  padding: 110px 20px;
  text-align: center;
  color: white;
  background:
    radial-gradient(circle at 20% 30%, rgba(200,155,60,0.15), transparent),
    radial-gradient(circle at 80% 70%, rgba(216,143,168,0.1), transparent),
    #07070b;
}

h2 {
  font-size: clamp(2rem, 4vw, 2.8rem);
  margin-bottom: 60px;
}

.fade {
  animation: fadeIn 0.5s ease;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(15px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.slider {
  position: relative;
  max-width: 650px;
  margin: auto;
}

.review-box {
  padding: 45px 35px;
  border-radius: 8px;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(226,201,121,0.18);
  backdrop-filter: blur(12px);
  transition: 0.3s;
}

.review-box:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 50px rgba(200,155,60,0.18);
}

.text {
  font-size: 1.3rem;
  color: #e5e0d6;
  margin-bottom: 20px;
}

h3 {
  font-size: 1.2rem;
  margin-bottom: 5px;
}

span {
  color: #bdb6aa;
}

.nav-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 44px;
  height: 44px;
  border-radius: 50%;
  border: 1px solid rgba(226,201,121,0.18);
  background: rgba(255,255,255,0.05);
  color: white;
  cursor: pointer;
  transition: 0.3s;
}

.nav-btn:hover {
  background: linear-gradient(135deg,var(--gold),var(--gold-light));
  color: #050507;
  transform: translateY(-50%) scale(1.1);
}

.left { left: -55px; }
.right { right: -55px; }

.all-reviews {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  max-width: 1100px;
  margin: auto;
}

.review-card {
  padding: 20px;
  border-radius: 8px;
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(226,201,121,0.14);
  transition: 0.3s;
}

.review-card:hover {
  transform: translateY(-5px);
  border-color: rgba(226,201,121,0.4);
}

.actions.center {
  margin-top: 60px;
  display: flex;
  justify-content: center;
}

.btn {
  padding: 14px 28px;
  border-radius: 8px;
  background: linear-gradient(90deg,var(--gold),var(--gold-light));
  color: #050507;
  border: none;
  cursor: pointer;
  font-weight: 800;
  transition: 0.3s;
}

.btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(200,155,60,0.3);
}

@media (max-width: 900px) {
  .review-box {
    padding: 25px;
  }

  .text {
    font-size: 1rem;
  }

  .all-reviews {
    grid-template-columns: 1fr;
  }

  .nav-btn {
    display: none;
  }
}
</style>
