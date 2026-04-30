<script setup>
</script>

<template>
  <section id="nosotros" class="about">

    <div class="container-global">

      <!-- TAG -->
      <p class="tag">SOBRE NOSOTROS</p>

      <!-- TITULO -->
      <h2>
        Transformamos ideas en <br>
        <span>resultados digitales reales</span>
      </h2>

      <!-- CONTENIDO -->
      <div class="about-content">

        <!-- TEXTO -->
        <div class="text">

          <h3>Somos un equipo enfocado en crear soluciones digitales de alto nivel</h3>

          <p>
            En VF Digital Services trabajamos con un enfoque profesional, estratégico y orientado a resultados.
            Nos especializamos en el desarrollo de soluciones web modernas que no solo se ven bien,
            sino que funcionan, convierten y generan crecimiento real para nuestros clientes.
          </p>

          <p>
            Cada proyecto lo desarrollamos con responsabilidad, atención al detalle y compromiso total.
            Entendemos que una página web no es solo diseño, es una herramienta clave para el crecimiento
            de cualquier negocio en el entorno digital.
          </p>

        </div>

        <!-- CARACTERISTICAS -->
        <div class="features">

          <div class="feature">
            <i class="fas fa-check-circle"></i>
            <div>
              <h4>Calidad Profesional</h4>
              <p>Diseños modernos, rápidos y optimizados para resultados reales.</p>
            </div>
          </div>

          <div class="feature">
            <i class="fas fa-bolt"></i>
            <div>
              <h4>Rendimiento y Velocidad</h4>
              <p>Webs optimizadas para cargar rápido y mejorar la experiencia del usuario.</p>
            </div>
          </div>

          <div class="feature">
            <i class="fas fa-users"></i>
            <div>
              <h4>Enfoque en el Cliente</h4>
              <p>Trabajamos contigo para entender tu negocio y llevarlo al siguiente nivel.</p>
            </div>
          </div>

          <div class="feature">
            <i class="fas fa-chart-line"></i>
            <div>
              <h4>Resultados Medibles</h4>
              <p>Desarrollamos estrategias enfocadas en crecimiento y conversión.</p>
            </div>
          </div>

        </div>

      </div>

    </div>

  </section>
</template>

<style scoped>

.about {
  padding: 120px 20px;
  color: white;

  background:
    radial-gradient(circle at 20% 30%, rgba(168,85,247,0.12), transparent),
    radial-gradient(circle at 80% 70%, rgba(59,130,246,0.12), transparent),
    #050507;
}

/* TAG */
.tag {
  text-align: center;
  color: #ec4899;
  margin-bottom: 10px;
  font-size: 0.9rem;
}

/* TITULO */
h2 {
  text-align: center;
  font-size: 2.8rem;
  margin-bottom: 70px;
  line-height: 1.3;
}

h2 span {
  background: linear-gradient(90deg,#a855f7,#3b82f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* LAYOUT */
.about-content {
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 60px;
  align-items: center;
}

/* TEXTO */
.text h3 {
  font-size: 1.6rem;
  margin-bottom: 20px;
}

.text p {
  color: #9ca3af;
  margin-bottom: 15px;
  line-height: 1.6;
}

/* FEATURES */
.features {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.feature {
  display: flex;
  gap: 15px;
  align-items: flex-start;

  background: rgba(255,255,255,0.02);
  border: 1px solid rgba(255,255,255,0.06);
  padding: 20px;
  border-radius: 12px;

  transition: 0.3s;
}

.feature:hover {
  transform: translateY(-5px);
  border-color: rgba(168,85,247,0.4);
}

/* ICONO */
.feature i {
  font-size: 22px;

  background: linear-gradient(90deg,#a855f7,#3b82f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* TEXTO */
.feature h4 {
  margin-bottom: 5px;
}

.feature p {
  color: #9ca3af;
  font-size: 0.9rem;
}

/* RESPONSIVE */
@media (max-width: 900px) {
  .about-content {
    grid-template-columns: 1fr;
  }

  h2 {
    font-size: 2.2rem;
  }
}

</style>