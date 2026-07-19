<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import logo from '../assets/logo.png'

const open = ref(false)
const emit = defineEmits(['open-contact', 'open-privacy'])

const openContact = () => {
  open.value = false
  emit('open-contact')
}

const openPrivacy = () => {
  open.value = false
  emit('open-privacy')
}

const handleClickOutside = (e) => {
  const menu = document.querySelector('.menu')
  const hamb = document.querySelector('.hamb')

  if (
    open.value &&
    menu &&
    !menu.contains(e.target) &&
    hamb &&
    !hamb.contains(e.target)
  ) {
    open.value = false
  }
}

onMounted(() => {
  document.addEventListener('click', handleClickOutside)
})

onBeforeUnmount(() => {
  document.removeEventListener('click', handleClickOutside)
})
</script>

<template>
  <header class="nav">
    <div class="wrap container-global">

      <a href="#" class="brand">
        <img :src="logo" alt="Instituto Eskareth">
      </a>

      <nav class="menu" :class="{ show: open }">
        <a href="#">Inicio</a>
        <a href="#nosotros">Nosotros</a>
        <a href="#servicios">Cursos</a>
        <a href="#" @click.prevent="openContact">Contacto</a>
        <a href="#" class="privacy" @click.prevent="openPrivacy">Privacidad</a>
      </nav>

      <a href="#" class="cta" @click.prevent="openContact">
        Solicitar información
      </a>

      <button class="hamb" @click="open = !open" aria-label="Abrir menú">
        ☰
      </button>

    </div>
  </header>
</template>

<style scoped>

.nav{
  position:fixed;
  top:0;
  width:100%;
  z-index:1000;
  background:rgba(5,5,7,.72);
  backdrop-filter:blur(12px);
  border-bottom:1px solid rgba(200,155,60,.18);
}

.wrap{
  height:90px;
  display:grid;
  grid-template-columns:auto 1fr auto auto;
  align-items:center;
  gap:30px;
}

.brand{
  display:flex;
  align-items:center;
  justify-content:center;
  text-decoration:none;
}

.brand img{
  height:75px;
  width:auto;
  display:block;
  transition:.3s;
}

.brand img:hover{
  transform:scale(1.05);
}

.menu{
  display:flex;
  justify-content:center;
  gap:26px;
}

.menu a{
  font-size:.95rem;
  color:#d8d8d8;
  text-decoration:none;
  font-weight:500;
  position:relative;
  transition:.25s;
}

.menu a::after{
  content:"";
  position:absolute;
  left:0;
  bottom:-6px;
  width:0;
  height:2px;
  background:var(--gold);
  transition:.25s;
}

.menu a:hover{
  color:white;
}

.menu a:hover::after{
  width:100%;
}

.privacy{
  font-size:.82rem;
  color:#9f9f9f;
}

.privacy:hover{
  color:var(--gold);
}

.cta{
  font-size:.9rem;
  padding:10px 18px;
  border-radius:8px;
  text-decoration:none;
  font-weight:700;
  color:#050507;
  background:var(--gold);
  transition:.25s;
}

.cta:hover{
  background:var(--gold-light);
  transform:translateY(-2px);
  box-shadow:0 8px 20px rgba(200,155,60,.30);
}

.hamb{
  display:none;
  background:none;
  border:none;
  color:white;
  font-size:1.4rem;
  cursor:pointer;
}

@media(max-width:900px){

  .nav{
    height:70px;
  }

  .wrap{
    height:70px;
    display:flex;
    justify-content:space-between;
    align-items:center;
  }

  .brand img{
    height:58px;
  }

  .menu{
    position:absolute;
    top:75px;
    right:15px;
    width:220px;
    display:none;
    flex-direction:column;
    background:rgba(10,10,10,.96);
    border:1px solid rgba(200,155,60,.15);
    border-radius:8px;
    padding:10px 0;
    backdrop-filter:blur(12px);
    box-shadow:0 10px 30px rgba(0,0,0,.55);
  }

  .menu.show{
    display:flex;
  }

  .menu a{
    padding:14px 20px;
  }

  .cta{
    display:none;
  }

  .hamb{
    display:block;
  }

}

</style>