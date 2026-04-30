<script setup>
import logo from '../assets/logo.png'
</script>

<template>
  <section class="hero">
    <div class="wrap container-global">

      <!-- TEXTO -->
      <div class="text fade-up">

        <h1>
          Servicios de Diseño Web <br>
          <span>& Marketing Digital</span>
        </h1>

        <p class="desc">
          Creamos páginas web modernas, rápidas y optimizadas para convertir visitantes en clientes reales.
        </p>

        <div class="actions">
          <a href="https://wa.me/5215618049841" target="_blank" class="btn primary">
            Contáctanos
          </a>

          <a href="#servicios" class="btn ghost">
            Ver servicios
          </a>
        </div>

      </div>

      <!-- LOGO + REDES -->
      <div class="visual fade-in">

        <img :src="logo" alt="logo">

        <!-- 🔥 TITULO REDES -->
        <p class="social-title">REDES</p>

        <!-- REDES -->
        <div class="socials">

          <a href="https://www.instagram.com/vf_digital_services" target="_blank" class="ig">
            <i class="fab fa-instagram"></i>
          </a>

          <a href="https://www.tiktok.com/@vfdigitalservicess" target="_blank" class="tt">
            <i class="fab fa-tiktok"></i>
          </a>

          <a href="https://wa.me/5215618049841" target="_blank" class="wa">
            <i class="fab fa-whatsapp"></i>
          </a>

        </div>

      </div>

    </div>

    <!-- BOTÓN FLOTANTE -->
    <a href="https://wa.me/5215618049841" class="whatsapp-float" target="_blank">
      <i class="fab fa-whatsapp"></i>
    </a>

  </section>
</template>

<style scoped>

/* 🔥 TITULO REDES */
.social-title {
  margin-top: 10px;
  font-size: 0.75rem;
  letter-spacing: 2px;
  color: #9ca3af;
  text-transform: uppercase;
}

/* ❌ QUITAR SUBRAYADO */
.socials a,
.socials a i {
  text-decoration: none;
}

.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  color: white;
  background:
    radial-gradient(circle at 25% 30%, rgba(168,85,247,0.18), transparent 50%),
    radial-gradient(circle at 75% 70%, rgba(59,130,246,0.18), transparent 50%),
    #050507;
}

.wrap {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 140px;
}

.text {
  max-width: 560px;
}

h1 {
  font-size: 3.8rem;
  line-height: 1.1;
  font-weight: 700;
  letter-spacing: 1px;
}

h1 span {
  background: linear-gradient(90deg,#a855f7,#3b82f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.desc {
  margin-top: 20px;
  color: #9ca3af;
  font-size: 1.1rem;
}

.actions {
  margin-top: 30px;
}

.btn {
  padding: 14px 24px;
  border-radius: 10px;
  margin-right: 12px;
  font-weight: 600;
  text-decoration: none;
}

.primary {
  background: linear-gradient(90deg,#a855f7,#3b82f6);
  color: white;
}

.ghost {
  border: 1px solid #a855f7;
  color: #a855f7;
}

/* LOGO */
.visual {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 15px;
}

.visual img {
  width: 620px;
  mix-blend-mode: screen;
  opacity: 0.95;
}

/* REDES */
.socials {
  display: flex;
  gap: 16px;
}

.socials a {
  width: 52px;
  height: 52px;
  border-radius: 14px;

  display: flex;
  align-items: center;
  justify-content: center;

  font-size: 20px;
  color: white;

  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);

  transition: 0.3s;
}

/* HOVER PRO */
.socials a.ig:hover {
  background: #E1306C;
  box-shadow: 0 0 20px #E1306C;
}

.socials a.tt:hover {
  background: #000;
  box-shadow: 0 0 20px #25F4EE;
}

.socials a.wa {
  background: #25D366;
}

.socials a.wa:hover {
  transform: scale(1.1);
  box-shadow: 0 0 20px #25D366;
}

/* FLOAT WHATSAPP */
.whatsapp-float {
  position: fixed;
  bottom: 25px;
  right: 25px;

  width: 65px;
  height: 65px;

  border-radius: 50%;
  background: #25D366;

  display: flex;
  align-items: center;
  justify-content: center;

  font-size: 28px;
  color: white;

  box-shadow: 0 10px 30px rgba(37,211,102,0.4);

  z-index: 999;
}

.whatsapp-float:hover {
  transform: scale(1.1);
}

/* ANIMACIONES */
.fade-up {
  animation: fadeUp 0.9s ease forwards;
}

.fade-in {
  animation: fadeIn 1.2s ease forwards;
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes fadeIn {
  from { opacity: 0; transform: scale(0.95); }
  to { opacity: 1; transform: scale(1); }
}

/* RESPONSIVE */
@media (max-width: 900px) {
  .wrap {
    flex-direction: column;
    text-align: center;
  }

  h1 {
    font-size: 2.6rem;
  }

  .visual img {
    width: 380px;
  }
}
</style>