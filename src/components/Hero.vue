<script setup>
import logo from '../assets/logo.png'
</script>

<template>

<section class="hero">

<div class="wrap container-global">

<div class="text fade-up">

<p class="eyebrow">
Instituto de Belleza Eskareth
</p>

<h1>
Aprende,<br>
practica y<br>
emprende<br>
en el mundo<br>
de la belleza
</h1>

<p class="desc">
Cursos profesionales de estilismo, barbería, maquillaje,
uñas, cejas y pestañas para convertir tu talento en una profesión.
</p>

<div class="actions">

<a
href="https://wa.me/5215519707045"
target="_blank"
class="btn primary"
>
Contáctanos
</a>

<a
href="#servicios"
class="btn ghost"
>
Ver cursos
</a>

</div>

<div class="stats">

<div>
<h4>1 a 6 meses</h4>
<p>Duración de los cursos</p>
</div>

<div>
<h4>Desde $1100</h4>
<p>Inversión</p>
</div>

<div>
<h4>SEP</h4>
<p>Constancia oficial</p>
</div>

</div>

</div>

<div class="visual fade-in">

<img
:src="logo"
alt="Instituto Eskareth"
/>

<p class="social-title">
ÁREAS DE FORMACIÓN
</p>

<div class="specialties">

<span>Cabello</span>

<span>Estética</span>

<span>Cejas y pestañas</span>

<span>Uñas</span>

<span>Maquillaje</span>

<span>Barbería</span>

</div>

</div>

</div>

<a
href="https://wa.me/5215519707045"
target="_blank"
class="whatsapp-float"
>

<i class="fab fa-whatsapp"></i>

</a>

</section>

</template>
<style>

a{
text-decoration:none!important;
}

.hero{

min-height:100vh;

display:flex;

align-items:center;

color:white;

background:
radial-gradient(circle at 18% 24%,rgba(200,155,60,.20),transparent 34%),
radial-gradient(circle at 78% 70%,rgba(216,143,168,.12),transparent 32%),
#050507;

position:relative;

overflow:hidden;

padding:110px 0 70px;

}

.hero::after{

content:"";

position:absolute;

inset:0;

background-image:
radial-gradient(rgba(226,201,121,.10) 1px,transparent 1px);

background-size:42px 42px;

opacity:.45;

z-index:0;

}

.wrap{

position:relative;

z-index:2;

display:grid;

grid-template-columns:.95fr 1.05fr;

align-items:center;

gap:80px;

}

.text{

max-width:540px;

}

.eyebrow{

color:var(--gold-light);

font-size:.82rem;

font-weight:700;

letter-spacing:.25em;

margin-bottom:20px;

text-transform:uppercase;

}

h1{

font-size:4.7rem;

line-height:.95;

font-weight:700;

margin-bottom:25px;

}

.desc{

color:#d8d0c2;

font-size:1.08rem;

line-height:1.8;

max-width:500px;

}

.actions{

margin-top:36px;

display:flex;

gap:16px;

flex-wrap:wrap;

}

.btn{

display:inline-flex;

align-items:center;

justify-content:center;

padding:14px 28px;

border-radius:10px;

font-weight:700;

transition:.25s;

min-height:50px;

}

.primary{

background:linear-gradient(135deg,var(--gold),var(--gold-light));

color:#050507;

}

.primary:hover{

transform:translateY(-3px);

}

.ghost{

border:1px solid rgba(226,201,121,.55);

color:var(--gold-light);

}

.ghost:hover{

background:rgba(226,201,121,.08);

}

.stats{

margin-top:45px;

display:grid;

grid-template-columns:repeat(3,1fr);

gap:15px;

}

.stats div{

padding:20px 15px;

background:rgba(255,255,255,.04);

border:1px solid rgba(226,201,121,.18);

border-radius:10px;

backdrop-filter:blur(8px);

}
.stats h4{

color:var(--gold-light);

font-size:1.35rem;

margin-bottom:8px;

}

.stats p{

color:#bdb6aa;

font-size:.86rem;

line-height:1.4;

}

.visual{

display:flex;

flex-direction:column;

align-items:center;

justify-content:center;

}

.visual img{

display:block;

width:520px;

max-width:100%;

margin:0 auto;

filter:
drop-shadow(0 25px 55px rgba(0,0,0,.55));

transition:.35s;

}

.visual img:hover{

transform:scale(1.03);

}

.social-title{

margin-top:10px;

margin-bottom:22px;

color:var(--gold-light);

font-size:.82rem;

font-weight:700;

letter-spacing:.20em;

text-align:center;

}

.specialties{

display:grid;

grid-template-columns:repeat(2,1fr);

gap:14px;

width:100%;

max-width:470px;

}

.specialties span{

display:flex;

align-items:center;

justify-content:center;

min-height:52px;

border-radius:10px;

background:rgba(255,255,255,.04);

border:1px solid rgba(226,201,121,.18);

color:#ece2d1;

font-weight:700;

cursor:pointer;

transition:.25s;

}

.specialties span:hover{

transform:translateY(-3px);

border-color:var(--gold);

background:rgba(226,201,121,.08);

box-shadow:0 10px 25px rgba(200,155,60,.18);

}

.whatsapp-float{

position:fixed;

bottom:22px;

right:22px;

width:62px;

height:62px;

border-radius:50%;

background:#25D366;

display:flex;

align-items:center;

justify-content:center;

font-size:30px;

color:white;

box-shadow:0 10px 30px rgba(37,211,102,.45);

z-index:9999;

transition:.3s;

}

.whatsapp-float:hover{

transform:scale(1.08);

box-shadow:0 0 35px #25D366;

}

.fade-up{

opacity:0;

transform:translateY(35px);

animation:fadeUp .9s ease forwards;

}

.fade-in{

opacity:0;

transform:scale(.97);

animation:fadeIn 1.1s ease forwards;

}

@keyframes fadeUp{

to{

opacity:1;

transform:translateY(0);

}

}

@keyframes fadeIn{

to{

opacity:1;

transform:scale(1);

}

}

@media(max-width:900px){

.hero{

padding:90px 0 70px;

}

.wrap{

grid-template-columns:1fr;

text-align:center;

gap:45px;

}

.text{

max-width:100%;

}

h1{

font-size:3.2rem;

}

.desc{

margin:auto;

}

.actions{

justify-content:center;

}

.stats{

grid-template-columns:1fr;

max-width:360px;

margin-left:auto;

margin-right:auto;

}

.visual{

order:-1;

}

.visual img{

width:300px;

}

.specialties{

max-width:360px;

margin:auto;

}

}

@media(max-width:520px){

.hero{

padding-top:80px;

}

h1{

font-size:2.45rem;

}

.actions{

flex-direction:column;

}

.btn{

width:100%;

}

.visual img{

width:240px;

}

.specialties{

grid-template-columns:1fr;

}

}

</style>