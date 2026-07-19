<script setup>
import { onMounted, onUnmounted } from 'vue'

const emit = defineEmits(['close'])

const handleKey = (e) => {
  if (e.key === 'Escape') emit('close')
}

onMounted(() => {
  document.body.style.overflow = 'hidden'
  window.addEventListener('keydown', handleKey)
})

onUnmounted(() => {
  document.body.style.overflow = 'auto'
  window.removeEventListener('keydown', handleKey)
})

const closeIfOutside = (e) => {
  if (e.target.classList.contains('overlay')) {
    emit('close')
  }
}
</script>

<template>
  <div class="overlay" @click="closeIfOutside">
    <section class="privacy">
      <button class="close" @click="emit('close')">x</button>

      <p class="updated">Ultima actualizacion: Abril 2026</p>

      <h2>Politica de Privacidad</h2>

      <div class="content">
        <p>
          En <strong>Instituto Eskareth</strong>, protegemos la informacion personal de alumnos, aspirantes y personas interesadas en nuestros cursos.
        </p>

        <h3>1. Responsable del tratamiento</h3>
        <p>
          Instituto Eskareth es responsable del uso y proteccion de los datos personales recabados a traves de este sitio.
        </p>

        <h3>2. Datos recopilados</h3>
        <p>
          Podemos recopilar nombre, correo electronico, numero telefonico y datos proporcionados voluntariamente al solicitar informacion.
        </p>

        <h3>3. Finalidad</h3>
        <p>
          Utilizamos los datos para atender solicitudes, brindar informacion de cursos, resolver dudas de inscripcion y dar seguimiento a contactos.
        </p>

        <h3>4. Seguridad de la informacion</h3>
        <p>
          Implementamos medidas razonables para proteger los datos contra acceso no autorizado, perdida o alteracion.
        </p>

        <h3>5. Transferencia de datos</h3>
        <p>
          No compartimos informacion personal con terceros, salvo cuando sea necesario para cumplir obligaciones legales.
        </p>

        <h3>6. Derechos ARCO</h3>
        <p>
          Puede acceder, rectificar, cancelar u oponerse al uso de sus datos personales contactandonos directamente.
        </p>

        <h3>7. Contacto</h3>
        <p>
          <strong>Email:</strong> institutoeskareth@gmail.com<br>
          <strong>Telefono:</strong> +52 1 55 1970 7045
        </p>
      </div>
    </section>
  </div>
</template>

<style scoped>
.overlay {
  position: fixed;
  inset: 0;
  z-index: 3000;
  background: rgba(0,0,0,0.85);
  backdrop-filter: blur(12px);
  display: flex;
  justify-content: center;
  align-items: center;
  animation: fadeIn 0.3s ease;
}

.privacy {
  width: 90%;
  max-width: 800px;
  max-height: 85vh;
  overflow-y: auto;
  background:
    radial-gradient(circle at 20% 30%, rgba(200,155,60,0.15), transparent),
    radial-gradient(circle at 80% 70%, rgba(216,143,168,0.1), transparent),
    #06060a;
  border: 1px solid rgba(226,201,121,0.18);
  border-radius: 8px;
  padding: 40px;
  color: white;
  position: relative;
  animation: slideUp 0.35s ease;
}

.close {
  position: absolute;
  top: 20px;
  right: 20px;
  width: 38px;
  height: 38px;
  border-radius: 8px;
  border: none;
  cursor: pointer;
  background: rgba(255,255,255,0.05);
  color: white;
  transition: 0.25s;
}

.close:hover {
  background: linear-gradient(90deg,var(--gold),var(--gold-light));
  color: #050507;
}

h2 {
  margin-bottom: 10px;
}

h3 {
  margin-top: 22px;
  color: var(--gold-light);
}

p {
  color: #cfc7ba;
  line-height: 1.6;
}

.updated {
  font-size: 0.8rem;
  color: #8f877a;
  margin-bottom: 10px;
}

@keyframes fadeIn {
  from { opacity: 0 }
  to { opacity: 1 }
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(40px) scale(0.95);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.privacy::-webkit-scrollbar {
  width: 6px;
}

.privacy::-webkit-scrollbar-thumb {
  background: var(--gold);
  border-radius: 10px;
}
</style>
