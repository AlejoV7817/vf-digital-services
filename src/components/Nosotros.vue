<template>
  <section id="nosotros" class="about">
    <div class="container-global">
      <p class="tag">SOBRE NOSOTROS</p>

      <h2>
        Formacion de belleza para aprender,
        practicar y emprender
      </h2>

      <div class="about-content">
        <div class="text">
          <h3>Instituto Eskareth acompaña tu crecimiento profesional</h3>

          <p>
            Preparamos a estudiantes que quieren iniciar o fortalecer su camino en el mundo de la belleza con clases practicas, herramientas profesionales y tecnicas aplicables desde el primer modulo.
          </p>

          <p>
            Nuestro enfoque combina estilismo, barberia, imagen personal y habilidades de emprendimiento para que cada alumno pueda construir su propio futuro con estilo.
          </p>
        </div>

        <div class="features">
          <div class="feature">
            <i class="fas fa-scissors"></i>
            <div>
              <h4>Practica constante</h4>
              <p>Aprende con ejercicios guiados, tecnicas reales y seguimiento durante tu proceso.</p>
            </div>
          </div>

          <div class="feature">
            <i class="fas fa-certificate"></i>
            <div>
              <h4>Constancia oficial SEP</h4>
              <p>Al concluir satisfactoriamente puedes tramitar tu constancia oficial de capacitacion.</p>
            </div>
          </div>

          <div class="feature">
            <i class="fas fa-calendar-check"></i>
            <div>
              <h4>Horarios accesibles</h4>
              <p>Curso de 6 meses con horarios flexibles para organizar mejor tu aprendizaje.</p>
            </div>
          </div>

          <div class="feature">
            <i class="fas fa-chart-line"></i>
            <div>
              <h4>Enfoque emprendedor</h4>
              <p>Impulsa tus conocimientos, tus habilidades y tu crecimiento profesional.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  padding: 110px 20px;
  color: white;
  background:
    linear-gradient(180deg, #050507, #0d0b08 48%, #050507);
}

.tag {
  text-align: center;
  color: var(--gold-light);
  margin-bottom: 12px;
  font-size: 0.86rem;
  font-weight: 700;
  letter-spacing: 0.2em;
}

h2 {
  max-width: 850px;
  margin: 0 auto 64px;
  text-align: center;
  font-size: clamp(2rem, 4vw, 3.35rem);
  line-height: 1.12;
}

.about-content {
  display: grid;
  grid-template-columns: 1.05fr 1fr;
  gap: 58px;
  align-items: center;
}

.text h3 {
  color: var(--gold-light);
  font-size: 1.55rem;
  margin-bottom: 20px;
}

.text p {
  color: #d2ccc3;
  margin-bottom: 16px;
  line-height: 1.75;
}

.features {
  display: grid;
  gap: 18px;
}

.feature {
  display: flex;
  gap: 16px;
  align-items: flex-start;
  min-height: 112px;
  background: rgba(255,255,255,0.035);
  border: 1px solid rgba(200,155,60,0.18);
  padding: 20px;
  border-radius: 8px;
  transition: 0.3s;
}

.feature:hover {
  transform: translateY(-4px);
  border-color: rgba(226,201,121,0.42);
}

.feature i {
  min-width: 24px;
  color: var(--gold-light);
  font-size: 22px;
  margin-top: 3px;
}

.feature h4 {
  margin-bottom: 6px;
}

.feature p {
  color: #bdb6aa;
  font-size: 0.92rem;
  line-height: 1.55;
}

@media (max-width: 900px) {
  .about {
    padding: 82px 20px;
  }

  .about-content {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .feature {
    text-align: left;
  }
}
</style>
