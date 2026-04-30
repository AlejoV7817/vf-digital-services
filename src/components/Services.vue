<template>
  <section id="servicios" class="services">

    <div class="container-global">

      <!-- 🔹 SECCIÓN PRINCIPAL -->
      <p class="tag">NUESTRA OFERTA DE VALOR</p>

      <h2>
        Ofrecemos una amplia <br>
        gama de <span>servicios digitales</span>
      </h2>

      <div class="cards">

        <!-- DISEÑO WEB -->
        <div class="card">
          <i class="fas fa-code"></i>
          <h3>Diseño Web Profesional</h3>
          <p>
            Creamos sitios web modernos, rápidos y optimizados para convertir visitas en clientes.
          </p>
        </div>

        <!-- FINANZAS -->
        <div class="card">
          <i class="fas fa-chart-line"></i>
          <h3>Finanzas & Trading</h3>
          <p>
            Aprende análisis gráfico y estrategias financieras con nuestros cursos especializados.
          </p>
        </div>

        <!-- MARKETING -->
        <div class="card">
          <i class="fas fa-bullseye"></i>
          <h3>Marketing Digital</h3>
          <p>
            Estrategias de publicidad online para hacer crecer tu negocio y aumentar tus ventas.
          </p>
        </div>

        <!-- SOPORTE -->
        <div class="card">
          <i class="fas fa-laptop-medical"></i>
          <h3>Soporte Técnico</h3>
          <p>
            Solucionamos problemas computacionales y optimizamos el rendimiento de tus equipos.
          </p>
        </div>

        <!-- HOSTING -->
        <div class="card">
          <i class="fas fa-server"></i>
          <h3>Hosting & Dominio</h3>
          <p>
            Configuramos tu sitio web con dominio propio y hosting rápido y seguro.
          </p>
        </div>

        <!-- ACTUALIZACIÓN -->
        <div class="card">
          <i class="fas fa-sync-alt"></i>
          <h3>Actualización Web</h3>
          <p>
            Mejoramos y actualizamos tu página para mantenerla moderna, rápida y funcional.
          </p>
        </div>

      </div>

      <!-- 🔥 NUEVA SECCIÓN -->
      <p class="tag extra">OTROS SERVICIOS</p>

      <div class="cards extra-cards">

        <div class="card">
          <i class="fas fa-search"></i>
          <h3>Posicionamiento en Google</h3>
          <p>
            Mejora la visibilidad de tu página web y aparece en los primeros resultados con estrategias SEO efectivas.
          </p>
        </div>

        <div class="card">
          <i class="fas fa-chart-pie"></i>
          <h3>Google Analytics & Stats</h3>
          <p>
            Analizamos el tráfico de tu sitio web para optimizar tu estrategia digital y tomar decisiones basadas en datos reales.
          </p>
        </div>

      </div>

      <!-- 🔥 COTIZACIÓN -->
      <div class="quote">

        <h3>¿Te gustaria contratar alguno de nuestros servicios?</h3>

        <p>
          Creamos soluciones digitales diseñadas para atraer clientes, aumentar tus ventas y hacer crecer tu negocio de forma real y medible.
        </p>

        <div class="price">
          Servicios web y de marketing desde  <span>$1,500</span> hasta <span>$7,000 MXN</span>
        </div>

        <a 
          href="https://wa.me/5215618049841?text=Hola,%20quiero%20cotizar%20una%20p%C3%A1gina%20web"
          target="_blank" 
          class="btn-quote"
        >
          Solicitar cotización
        </a>

      </div>

    </div>

  </section>
</template>

<style scoped>
.services {
  padding: 120px 20px;
  color: white;
  text-align: center;

  /* 🔥 FONDO PROFESIONAL */
  background:
    radial-gradient(circle at 20% 30%, rgba(168,85,247,0.12), transparent 50%),
    radial-gradient(circle at 80% 70%, rgba(59,130,246,0.12), transparent 50%),
    linear-gradient(to bottom, #050507, #06060a);
}

/* TAG */
.tag {
  color: #ec4899;
  font-size: 0.85rem;
  margin-bottom: 10px;
}

.tag.extra {
  margin-top: 80px;
}

/* TITULO */
h2 {
  font-size: 2.8rem;
  margin-bottom: 70px;
  line-height: 1.3;
}

h2 span {
  color: white;
  font-weight: 700;
}

/* CARDS */
.cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
}

.extra-cards {
  grid-template-columns: repeat(2, 1fr);
  max-width: 800px;
  margin: auto;
}

/* CARD */
.card {
  background: rgba(255,255,255,0.02);
  border: 1px solid rgba(255,255,255,0.06);
  padding: 40px 30px;
  border-radius: 16px;
  transition: all 0.3s ease;
  min-height: 260px;
}

.card:hover {
  transform: translateY(-8px);
  border-color: rgba(168,85,247,0.4);
  box-shadow: 0 10px 30px rgba(168,85,247,0.15);
}

/* ICONOS */
.card i {
  font-size: 40px;
  margin-bottom: 20px;

  background: linear-gradient(90deg,#a855f7,#3b82f6);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* TEXTO */
.card h3 {
  margin-bottom: 12px;
  font-size: 1.1rem;
}

.card p {
  font-size: 0.9rem;
  color: #9ca3af;
}

/* 🔥 COTIZACIÓN */
.quote {
  margin-top: 100px;
  padding: 50px 30px;
  border-radius: 20px;

  background:
    radial-gradient(circle at 30% 20%, rgba(168,85,247,0.2), transparent),
    radial-gradient(circle at 70% 80%, rgba(59,130,246,0.2), transparent),
    rgba(255,255,255,0.02);

  border: 1px solid rgba(255,255,255,0.08);
}

.quote h3 {
  font-size: 1.8rem;
  margin-bottom: 15px;
}

.quote p {
  color: #9ca3af;
  margin-bottom: 25px;
}

.price {
  font-size: 1.4rem;
  margin-bottom: 30px;
}

.price span {
  font-weight: 700;
  background: linear-gradient(90deg,#a855f7,#3b82f6);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* BOTÓN */
.btn-quote {
  display: inline-block;
  padding: 14px 30px;
  border-radius: 10px;
  text-decoration: none;

  background: linear-gradient(90deg,#a855f7,#3b82f6);
  color: white;
  font-weight: 600;

  transition: all 0.25s ease;
}

.btn-quote:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(168,85,247,0.4);
}

/* RESPONSIVE */
@media (max-width: 900px) {
  .cards,
  .extra-cards {
    grid-template-columns: 1fr;
  }
}
</style>