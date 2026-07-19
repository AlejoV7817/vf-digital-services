<script setup>
import { onMounted, onUnmounted } from 'vue'

const emit = defineEmits(['close'])

const handleKey = (e) => {
  if (e.key === 'Escape') {
    emit('close')
  }
}

const closeIfOutside = (e) => {
  if (e.target.classList.contains('overlay')) {
    emit('close')
  }
}

onMounted(() => {
  document.body.style.overflow = 'hidden'
  window.addEventListener('keydown', handleKey)
})

onUnmounted(() => {
  document.body.style.overflow = 'auto'
  window.removeEventListener('keydown', handleKey)
})
</script>
<template>
  <div class="overlay" @click="closeIfOutside">
    <section class="contact">

      <button
        class="close"
        @click="emit('close')"
      >
        ×
      </button>

      <p class="tag">
        CONTACTO
      </p>

      <h2>
        Solicita información para tu
        <span>inscripción</span>
      </h2>

      <p class="desc">
        Estamos listos para ayudarte a comenzar tu formación profesional.
        Contáctanos para conocer nuestros cursos, costos, promociones,
        proceso de inscripción y resolver cualquier duda.
      </p>

      <div class="contact-grid">

        <!-- EMAIL -->

        <a
          href="mailto:institutoeskareth@gmail.com"
          class="contact-card"
        >

          <i class="fas fa-envelope"></i>

          <h3>
            Email
          </h3>

          <p>
            institutoeskareth@gmail.com
          </p>

        </a>

        <!-- WHATSAPP -->

        <a
          href="https://wa.me/5215519707045?text=Hola,%20quiero%20información%20sobre%20los%20cursos%20del%20Instituto%20de%20Belleza%20Eskareth"
          target="_blank"
          class="contact-card"
        >

          <i class="fab fa-whatsapp"></i>

          <h3>
            WhatsApp
          </h3>

          <p>
            +52 1 55 1970 7045
          </p>

        </a>

        <!-- BENEFICIOS -->

        <div class="contact-card">

          <i class="fas fa-graduation-cap"></i>

          <h3>
            ¿Por qué elegirnos?
          </h3>

          <p>

            ✔ Clases 90% prácticas

            <br>

            ✔ Atención personalizada

            <br>

            ✔ Formación para emprender

          </p>

        </div>

        <!-- REDES -->

        <div class="contact-card social">

          <i class="fas fa-share-alt"></i>

          <h3>
            Redes Sociales
          </h3>

          <div class="social-links">

            <a
              href="https://www.facebook.com/share/1JJkbqpkMi/"
              target="_blank"
            >
              <i class="fab fa-facebook-f"></i>
            </a>

            <a
              href="https://www.instagram.com/escuela_de_belleza_eskareth?igsh=ZTQzeDBzaDdhczh4"
              target="_blank"
            >
              <i class="fab fa-instagram"></i>
            </a>

            <a
              href="https://wa.me/5215519707045"
              target="_blank"
            >
              <i class="fab fa-whatsapp"></i>
            </a>

          </div>

        </div>

      </div>

    </section>
  </div>
</template>
<style scoped>
.overlay {
  position: fixed;
  inset: 0;
  z-index: 9999;
  background: rgba(0, 0, 0, 0.9);
  backdrop-filter: blur(12px);
  overflow-y: auto;
  overflow-x: hidden;
  -webkit-overflow-scrolling: touch;
  touch-action: pan-y;
  padding: 90px 18px 40px;
  animation: fadeIn .35s ease;
}

.overlay::-webkit-scrollbar {
  width: 0;
}

.contact {
  width: 100%;
  max-width: 980px;
  margin: auto;
  padding: 55px 40px;
  border-radius: 18px;
  text-align: center;
  color: #fff;
  position: relative;
  overflow: hidden;

  background:
    radial-gradient(circle at top left, rgba(226,201,121,.12), transparent 35%),
    radial-gradient(circle at bottom right, rgba(226,201,121,.08), transparent 35%),
    linear-gradient(180deg,#0b0b0d,#050507);

  border: 1px solid rgba(226,201,121,.18);

  box-shadow:
    0 25px 70px rgba(0,0,0,.55),
    inset 0 1px 0 rgba(255,255,255,.04);

  animation: scaleIn .35s ease;
}

.close{
  position:absolute;
  top:20px;
  right:20px;
  width:48px;
  height:48px;
  border:none;
  border-radius:12px;
  background:rgba(255,255,255,.05);
  border:1px solid rgba(226,201,121,.18);
  color:#fff;
  font-size:22px;
  cursor:pointer;
  display:flex;
  align-items:center;
  justify-content:center;
  transition:.3s;
}

.close:hover{
  transform:rotate(90deg);
  background:linear-gradient(135deg,var(--gold),var(--gold-light));
  color:#050507;
}

.tag{
  display:inline-block;
  margin-bottom:18px;
  color:var(--gold-light);
  font-size:.85rem;
  font-weight:700;
  letter-spacing:.35em;
}

h2{
  font-size:clamp(2.2rem,5vw,3.4rem);
  line-height:1.1;
  margin-bottom:22px;
  font-weight:800;
}

h2 span{
  background:linear-gradient(90deg,var(--gold),var(--gold-light));
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}

.desc{
  max-width:720px;
  margin:0 auto 55px;
  color:#c8c8c8;
  line-height:1.9;
  font-size:1.05rem;
}

.contact-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:24px;
}

.contact-card{
  background:linear-gradient(
      180deg,
      rgba(255,255,255,.05),
      rgba(255,255,255,.02)
  );
  border:1px solid rgba(226,201,121,.16);
  border-radius:16px;
  padding:34px 24px;
  text-decoration:none;
  color:#fff;
  transition:.35s;
  overflow:hidden;
  position:relative;
}

.contact-card:hover{
  transform:translateY(-8px);
  border-color:var(--gold-light);
  box-shadow:0 20px 40px rgba(200,155,60,.2);
}

.contact-card i{
  width:70px;
  height:70px;
  margin:0 auto 20px;
  display:flex;
  align-items:center;
  justify-content:center;
  border-radius:50%;
  background:rgba(226,201,121,.08);
  border:1px solid rgba(226,201,121,.18);
  color:var(--gold-light);
  font-size:28px;
}

.contact-card h3{
  font-size:1.35rem;
  margin-bottom:14px;
  font-weight:700;
}

.contact-card p{
  color:#d6d6d6;
  line-height:1.75;
  font-size:.97rem;
}

.social-links{
  display:flex;
  justify-content:center;
  gap:16px;
  margin-top:20px;
  flex-wrap:wrap;
}

.social-links a{
  width:52px;
  height:52px;
  display:flex;
  justify-content:center;
  align-items:center;
  border-radius:12px;
  background:rgba(255,255,255,.05);
  border:1px solid rgba(226,201,121,.18);
  transition:.3s;
}

.social-links a:hover{
  transform:translateY(-4px);
  background:linear-gradient(135deg,var(--gold),var(--gold-light));
}

.social-links a i{
  margin:0;
  font-size:20px;
}

.social-links a:hover i{
  color:#050507;
}
@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

@keyframes scaleIn {
  from {
    opacity: 0;
    transform: scale(.94);
  }

  to {
    opacity: 1;
    transform: scale(1);
  }
}

@media (max-width:1120px){

  .contact-grid{
    grid-template-columns:repeat(2,1fr);
  }

}

@media (max-width:900px){

  .overlay{
    padding:80px 16px 110px;
  }

  .contact{

    padding:40px 24px;

    border-radius:16px;

  }

  h2{

    font-size:2rem;

  }

  .desc{

    font-size:.96rem;

    margin-bottom:40px;

  }

  .contact-grid{

    grid-template-columns:1fr;

    gap:18px;

  }

  .contact-card{

    padding:28px 22px;

  }

  .contact-card h3{

    font-size:1.2rem;

  }

  .contact-card p{

    font-size:.95rem;

  }

  .close{

    width:44px;

    height:44px;

    font-size:20px;

    top:16px;

    right:16px;

  }

}

@media (max-width:480px){

  .overlay{

    padding:70px 12px 90px;

  }

  .contact{

    padding:32px 18px;

  }

  .tag{

    font-size:.75rem;

    letter-spacing:.28em;

  }

  h2{

    font-size:1.7rem;

  }

  .desc{

    line-height:1.7;

  }

  .contact-card{

    padding:24px 18px;

  }

  .contact-card i{

    width:62px;

    height:62px;

    font-size:24px;

  }

}

</style>