<script setup>
import { ref } from "vue";

const whatsapp = "https://wa.me/5215546529662";

const openCourse = ref(null);

const toggleCourse = (index) => {
  openCourse.value =
    openCourse.value === index ? null : index;
};
const courses = [
{
title: "Curso de Estilismo Profesional",
icon: "fas fa-scissors",
duration: "6 meses",
price: "$1,800 mensuales",

description:
"Conviértete en estilista profesional aprendiendo técnicas modernas para dama, caballero y niño con un sistema práctico y personalizado.",

learn: [
"Técnicas de degradado",
"Puntado y texturizado",
"Técnica de grados",
"Uso correcto de tijeras",
"Navaja libre",
"Técnicas de textura",
"Corte para dama",
"Corte para caballero",
"Corte infantil",
"Tendencias actuales"
],

benefits: [
"Modalidad personalizada",
"Prácticas durante todo el curso",
"Atención individual",
"Preparación para trabajar en estética",
"Desarrollo de confianza profesional"
],

info: [
{
title:"Duración",
value:"6 meses"
},
{
title:"Inversión",
value:"$1,800 mensuales"
},
{
title:"Modalidad",
value:"Personalizada"
}
]
},

{
title:"Curso Profesional de Uñas",

icon:"fas fa-hand-sparkles",

duration:"1 mes",

price:"$4,300",

description:
"Aprende desde cero hasta técnicas avanzadas con un curso intensivo completamente práctico.",

learn:[

"Aplicación correcta",

"Perlas perfectas",

"Uso de monómero",

"Tip",

"Escultural",

"Encapsulados",

"Baby Boomer",

"3D",

"4D",

"5D",

"Mano alzada",

"Sellado de cutícula",

"Retoque",

"Retiro correcto"

],

includes:[

"Más de 180 horas",

"10 clases extra",

"Kit MC Profesional",

"Asesoría personalizada",

"Material para prácticas"

],

kit:[

"Monómero",

"Acrílicos",

"Pincel",

"Tips",

"Limas",

"Primer",

"Top Coat",

"Gel",

"Empujador",

"Corta tips"

],

info:[

{
title:"Duración",
value:"1 mes"
},

{
title:"Costo",
value:"$4,300"
},

{
title:"Modalidad",
value:"Personalizada"
}

]

},

{

title:"Curso Cultura de Belleza",

icon:"fas fa-crown",

duration:"10 meses",

price:"$1,180 cada 4 semanas",

description:
"Programa completo para formarte como profesional de la belleza con más de 36 temas y práctica constante.",

modules:[

"Maquillaje",

"Colorimetría",

"Alto peinado",

"Manicure",

"Pedicure",

"Spa",

"Limpieza facial",

"Depilación",

"Extensiones",

"Tratamientos capilares",

"Alaciados",

"Estilista diseñador"

],

benefits:[

"Más de 36 temas",

"90% práctica",

"Diploma",

"Certificado",

"Reconocimiento de estudios",

"Preparación para emprender"

],

info:[

{
title:"Duración",
value:"10 meses"
},

{
title:"Inversión",
value:"$1,180 cada 4 semanas"
},

{
title:"Modalidad",
value:"Personalizada"
}

]

}

];
</script>
<template>

<section id="servicios" class="services">

  <div class="container-global">

    <p class="tag">
      CURSOS PROFESIONALES
    </p>

    <h2>
      Aprende una profesión y
      <span>transforma tu futuro.</span>
    </h2>

    <p class="subtitle">
      En Instituto de Belleza Eskareth contamos con programas profesionales,
      atención personalizada y una formación enfocada en la práctica para que
      puedas comenzar tu carrera en el mundo de la belleza.
    </p>

    <div class="categories">

      <div
        class="service-box"
       v-for="(course,index) in courses"
:key="course.title"
      >

        <div class="icon">
          <i :class="course.icon"></i>
        </div>

        <h3>
          {{ course.title }}
        </h3>

        <p>
          {{ course.description }}
        </p>

      <details
  class="category-dropdown"
  :open="openCourse === index"
>

<summary
  @click.prevent="toggleCourse(index)"
>

<div class="summary-content">

<span>

Ver información completa

</span>

<span class="summary-icon">

{{ openCourse === index ? "−" : "+" }}

</span>

</div>

</summary>

          <div class="products">

            <div class="package featured">

              <div class="product-top">

                <span class="dot gold"></span>

                <h4>
                  Información General
                </h4>

              </div>

              <ul>

                <li
                  v-for="item in course.info"
                  :key="item.title"
                >

                  <strong>{{ item.title }}:</strong>

                  {{ item.value }}

                </li>

              </ul>

            </div>

            <div
              class="package"
              v-if="course.learn"
            >

              <div class="product-top">

                <span class="dot gold"></span>

                <h4>

                  ¿Qué aprenderás?

                </h4>

              </div>

              <ul>

                <li
                  v-for="item in course.learn"
                  :key="item"
                >

                  {{ item }}

                </li>

              </ul>

            </div>
                        <div
              class="package"
              v-if="course.modules"
            >

              <div class="product-top">

                <span class="dot gold"></span>

                <h4>
                  Temario del Curso
                </h4>

              </div>

              <ul>

                <li
                  v-for="item in course.modules"
                  :key="item"
                >
                  {{ item }}
                </li>

              </ul>

            </div>

            <div
              class="package"
              v-if="course.benefits"
            >

              <div class="product-top">

                <span class="dot gold"></span>

                <h4>
                  Beneficios
                </h4>

              </div>

              <ul>

                <li
                  v-for="item in course.benefits"
                  :key="item"
                >
                  {{ item }}
                </li>

              </ul>

            </div>

            <div
              class="package"
              v-if="course.includes"
            >

              <div class="product-top">

                <span class="dot gold"></span>

                <h4>
                  Incluye
                </h4>

              </div>

              <ul>

                <li
                  v-for="item in course.includes"
                  :key="item"
                >
                  {{ item }}
                </li>

              </ul>

            </div>

            <div
              class="package"
              v-if="course.kit"
            >

              <div class="product-top">

                <span class="dot gold"></span>

                <h4>
                  Tu kit incluye
                </h4>

              </div>

              <ul>

                <li
                  v-for="item in course.kit"
                  :key="item"
                >
                  {{ item }}
                </li>

              </ul>

            </div>

            <a
              :href="whatsapp"
              target="_blank"
              class="btn-quote"
            >
              Solicitar información por WhatsApp
            </a>

          </div>

        </details>

      </div>

    </div>

  </div>

</section>

</template>
<style scoped>

.services{
  position:relative;
  padding:120px 30px;
  background:#080808;
  overflow:hidden;
}

.container-global{
  max-width:1350px;
  margin:auto;
}

.tag{
  text-align:center;
  color:var(--gold-light,#d4af37);
  letter-spacing:.25em;
  text-transform:uppercase;
  font-size:.85rem;
  font-weight:700;
  margin-bottom:15px;
}

h2{
  text-align:center;
  color:#fff;
  font-size:3.2rem;
  line-height:1.2;
  margin-bottom:20px;
}

h2 span{
  color:var(--gold-light,#d4af37);
}

.subtitle{
  max-width:760px;
  margin:0 auto 70px;
  text-align:center;
  color:#d2d2d2;
  line-height:1.8;
  font-size:1.05rem;
}

.categories{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(360px,1fr));
  gap:35px;
}

.service-box{
  background:#111;
  border:1px solid rgba(212,175,55,.18);
  border-radius:18px;
  padding:35px;
  transition:.35s;
}

.service-box:hover{
  transform:translateY(-8px);
  border-color:#d4af37;
  box-shadow:0 20px 50px rgba(212,175,55,.15);
}

.icon{
  width:78px;
  height:78px;
  margin:auto auto 25px;
  border-radius:18px;
  display:flex;
  justify-content:center;
  align-items:center;
  background:rgba(212,175,55,.08);
  border:1px solid rgba(212,175,55,.18);
}

.icon i{
  color:#d4af37;
  font-size:34px;
}

.service-box h3{
  text-align:center;
  color:#fff;
  margin-bottom:18px;
  font-size:1.5rem;
}

.service-box p{
  text-align:center;
  color:#d8d8d8;
  line-height:1.8;
  margin-bottom:25px;
}

.category-dropdown{
  margin-top:20px;
}

.category-dropdown summary{
  cursor:pointer;
  list-style:none;
  padding:15px;
  border-radius:12px;
  background:#181818;
  border:1px solid rgba(212,175,55,.20);
  color:#d4af37;
  font-weight:700;
  text-align:center;
  transition:.3s;
}
.summary-content{

display:flex;

justify-content:space-between;

align-items:center;

width:100%;

}

.summary-icon{

font-size:24px;

font-weight:700;

color:#d4af37;

transition:.3s;

}


.category-dropdown summary::-webkit-details-marker{
  display:none;
}

.category-dropdown summary:hover{
  background:#202020;
}

.category-dropdown[open] summary{
  margin-bottom:20px;
}

.products{
  display:grid;
  gap:18px;
}

.package{
  background:#151515;
  border:1px solid rgba(212,175,55,.12);
  border-radius:14px;
  padding:22px;
}

.featured{
  border-color:#d4af37;
}

.product-top{
  display:flex;
  align-items:center;
  gap:12px;
  margin-bottom:18px;
}

.dot{
  width:12px;
  height:12px;
  border-radius:50%;
}

.gold{
  background:#d4af37;
}

.package h4{
  color:#fff;
  font-size:1.05rem;
}

.package ul{
  margin:0;
  padding-left:18px;
}

.package li{
  margin-bottom:10px;
  color:#ddd;
  line-height:1.7;
}

.package strong{
  color:#d4af37;
}

.btn-quote{
  display:flex;
  justify-content:center;
  align-items:center;
  margin-top:25px;
  text-decoration:none;
  padding:15px;
  border-radius:12px;
  background:linear-gradient(135deg,#b8860b,#e8c65d);
  color:#000;
  font-weight:700;
  transition:.3s;
}

.btn-quote:hover{
  transform:translateY(-4px);
  box-shadow:0 15px 35px rgba(212,175,55,.25);
}

.category-dropdown[open]{
  animation:fadeIn .35s ease;
}

@keyframes fadeIn{

  from{
    opacity:0;
    transform:translateY(-8px);
  }

  to{
    opacity:1;
    transform:translateY(0);
  }

}

.service-box,
.package,
.btn-quote{
  transition:all .35s ease;
}

.package:hover{
  border-color:rgba(212,175,55,.35);
  transform:translateY(-3px);
}

.service-box h3,
.package h4{
  letter-spacing:.3px;
}

.package ul li::marker{
  color:#d4af37;
}

.btn-quote:active{
  transform:scale(.98);
}

@media (max-width:1200px){

  .categories{
    grid-template-columns:repeat(2,1fr);
  }

}

@media (max-width:900px){

  .services{
    padding:100px 24px;
  }

  h2{
    font-size:2.5rem;
  }

  .subtitle{
    margin-bottom:50px;
  }

  .categories{
    grid-template-columns:1fr;
  }

}

@media (max-width:600px){

  .services{
    padding:80px 18px;
  }

  h2{
    font-size:2rem;
  }

  .tag{
    font-size:.75rem;
    letter-spacing:.18em;
  }

  .subtitle{
    font-size:.95rem;
    line-height:1.7;
  }

  .service-box{
    padding:26px 20px;
  }

  .icon{
    width:64px;
    height:64px;
  }

  .icon i{
    font-size:28px;
  }

  .service-box h3{
    font-size:1.25rem;
  }

  .package{
    padding:18px;
  }

  .btn-quote{
    width:100%;
    padding:16px;
  }

}

</style>