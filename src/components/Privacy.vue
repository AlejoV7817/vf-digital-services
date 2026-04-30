<script setup>
import { onMounted, onUnmounted } from 'vue'

const emit = defineEmits(['close'])

// cerrar con ESC
const handleKey = (e) => {
  if (e.key === 'Escape') emit('close')
}

// bloquear scroll
onMounted(() => {
  document.body.style.overflow = 'hidden'
  window.addEventListener('keydown', handleKey)
})

onUnmounted(() => {
  document.body.style.overflow = 'auto'
  window.removeEventListener('keydown', handleKey)
})

// click fuera
const closeIfOutside = (e) => {
  if (e.target.classList.contains('overlay')) {
    emit('close')
  }
}
</script>

<template>
  <div class="overlay" @click="closeIfOutside">

    <section class="privacy">

      <button class="close" @click="emit('close')">✕</button>

      <p class="updated">Última actualización: Abril 2026</p>

      <h2>Política de Privacidad</h2>

      <div class="content">

        <p>
          En <strong>VF Digital Services</strong>, protegemos la información personal de nuestros usuarios
          y garantizamos un tratamiento responsable conforme a la legislación mexicana.
        </p>

        <h3>1. Responsable del tratamiento</h3>
        <p>
          VF Digital Services es responsable del uso y protección de los datos personales recabados a través de este sitio.
        </p>

        <h3>2. Datos recopilados</h3>
        <p>
          Podemos recopilar nombre, correo electrónico, número telefónico y cualquier información
          proporcionada voluntariamente por el usuario.
        </p>

        <h3>3. Finalidad</h3>
        <p>
          Utilizamos los datos para:
          <br>• Atender solicitudes y consultas
          <br>• Brindar información de servicios
          <br>• Realizar cotizaciones
          <br>• Mejorar la experiencia del usuario
        </p>

        <h3>4. Seguridad de la información</h3>
        <p>
          Implementamos medidas de seguridad para proteger los datos contra acceso no autorizado,
          pérdida o alteración.
        </p>

        <h3>5. Transferencia de datos</h3>
        <p>
          No compartimos información personal con terceros, salvo cuando sea necesario
          para cumplir obligaciones legales o brindar un servicio solicitado.
        </p>

        <h3>6. Cookies y tecnologías</h3>
        <p>
          Utilizamos cookies para mejorar la experiencia del usuario y analizar el comportamiento del sitio.
        </p>

        <h3>7. Derechos ARCO</h3>
        <p>
          Usted puede Acceder, Rectificar, Cancelar u Oponerse al uso de sus datos personales
          contactándonos directamente.
        </p>

        <h3>8. Cambios en la política</h3>
        <p>
          Esta política puede actualizarse en cualquier momento. Las modificaciones serán visibles en este sitio.
        </p>

        <h3>9. Contacto</h3>
        <p>
          <strong>Email:</strong> vfdigitalservicess@gmail.com<br>
          <strong>Teléfono:</strong> +52 5618049841
        </p>

      </div>

    </section>

  </div>
</template>

<style scoped>

/* 🔥 OVERLAY */
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

/* 🔥 CONTENEDOR */
.privacy {
  width: 90%;
  max-width: 800px;
  max-height: 85vh;
  overflow-y: auto;

  background:
    radial-gradient(circle at 20% 30%, rgba(168,85,247,0.15), transparent),
    radial-gradient(circle at 80% 70%, rgba(59,130,246,0.15), transparent),
    #06060a;

  border-radius: 18px;
  padding: 40px;
  color: white;

  position: relative;

  animation: slideUp 0.35s ease;
}

/* BOTÓN */
.close {
  position: absolute;
  top: 20px;
  right: 20px;

  width: 38px;
  height: 38px;

  border-radius: 10px;
  border: none;
  cursor: pointer;

  background: rgba(255,255,255,0.05);
  color: white;

  transition: 0.25s;
}

.close:hover {
  background: linear-gradient(90deg,#a855f7,#3b82f6);
}

/* TITULOS */
h2 {
  margin-bottom: 10px;
}

h3 {
  margin-top: 22px;
}

/* TEXTO */
p {
  color: #9ca3af;
  line-height: 1.6;
}

/* UPDATED */
.updated {
  font-size: 0.8rem;
  color: #6b7280;
  margin-bottom: 10px;
}

/* ANIMACIONES */
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

/* SCROLL BAR */
.privacy::-webkit-scrollbar {
  width: 6px;
}

.privacy::-webkit-scrollbar-thumb {
  background: #a855f7;
  border-radius: 10px;
}

</style>