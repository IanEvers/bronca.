<template>

  <div>

    <Header />

    <div>
    
      <section id="home"> 
        
        <div class="nombreYFoto">
          <div>
            <h1> Catalina Rohde </h1>
            <h2> Hace cine</h2>
          </div>
          <div class="flex-center">
            <img src="./assets/cata.jpeg" alt="" class="imagenCata">
          </div>
        </div>

        <p>
          En el transcurso de los dos años de carrera tuve la
          oportunidad de realizar el montaje de un corto, tomar
          el rol de cámara durante la pandemia desde mi casa en
          otro y recientemente realice la producción de un corto
          de cinco minutos como trabajo final de la materia
          Proyecto Audiovisual I. Aparte de la facultad edito reels
          para actores y videos de quince. 
        </p>
      </section>

      <hr>

      <section id="proyectos">
        <h1 class="titulo"> Proyectos </h1>

        <div style="padding:56.25% 0 0 0;position:relative;" class="videoSeccion"><iframe src="https://player.vimeo.com/video/690584333?h=4fb3c3b042&title=0&byline=0&portrait=0" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture"></iframe></div>

        <div style="padding:56.25% 0 0 0;position:relative;" class="videoSeccion"><iframe src="https://player.vimeo.com/video/516059566?h=a431f82e3c&title=0&byline=0&portrait=0" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture"></iframe></div>
      
      </section>

      <hr>

      <section id="fotos">
        <h1 class="titulo"> Fotos </h1>

        <div class="gridFotos">
          <img v-for="foto in fotos" :src="foto.url" class="fotoSeccion" :class="foto.nombre">
        </div>
      </section>

      <hr>

      <SeccionContacto />

    </div>

    <Footer></Footer>

    <!-- <a href="#home" class="backTop"> Inicio </a> -->

  </div>
</template>


<script setup>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";

import img1 from './assets/fotos/foto1.jpg'
import img2 from './assets/fotos/foto2.png'
import img3 from './assets/fotos/foto3.jpg'
import img4 from './assets/fotos/foto4.jpg'
import img5 from './assets/fotos/foto5.jpg'
import img6 from './assets/fotos/foto6.jpg'
import SeccionContacto from './components/seccionContacto.vue'

const fotos = 
[
  {
    nombre: 'foto1',
    url: img1,
  },
  {
    nombre: 'foto2',
    url: img2,
  },
  {
    nombre: 'foto3',
    url: img3,
  },
  {
    nombre: 'foto4',
    url: img4,
  },
  {
    nombre: 'foto5',
    url: img5,
  },
  {
    nombre: 'foto6',
    url: img6,
  },
]

</script>

<style>

@font-face {
  font-family: 'Montserrat';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: url('assets/fonts/Montserrat-VariableFont_wght.ttf') format('truetype');
}

html {
  scroll-behavior:smooth
}

body {
  font-family: 'Montserrat', sans-serif;
  line-height: 1.2;
  margin: 0;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #0d1118;
}

.flex-center {
  display: flex;
  justify-content: center;
}

/* .backTop {
  position: sticky;
  bottom: 20px;      
  margin-right:30px; 
  left: 85vw;
  margin-top: calc(100vh + 700px);
  
  
  text-decoration: none;
  padding: 15px;
  font-family: sans-serif;
  color: #fff;
  background: #000;
  border-radius: 100px;
  white-space: nowrap;
} */

section {
  min-height: 70vh;
  padding: 1rem;
  max-width: 1024px;
  margin: auto;
}

hr {
  max-width: 80vw;
}

.titulo {
  text-align: center;
}

.imagenCata {
  margin: 1rem;
  max-width: 100vw;
}

p {
  font-size: 1.1rem;
  line-height: 1.4;
}

h1 {
  font-size: 2rem;
  margin: 0;
  padding: 0.3rem;
}

h2 {
  font-size: 1.5rem;
  font-weight: 200;
  margin: 0;
  padding: 0.3rem;
}

#fotos {
  margin-top: 2rem;
  padding: 0;
}

.fotoSeccion {
  max-width: 100vw;
  margin: auto;
}

.gridFotos {
  margin-top: 2rem;
  margin-bottom: 2rem;
}

.videoSeccion {
  margin: 3rem auto;
}

@media (min-width: 640px) {
  .nombreYFoto {
    display: flex;
    justify-content: space-between;
  }

  .imagenCata {
    max-width: 256px;
    margin: 0.5rem;
  }

  section {
    padding: 2rem;
  }

}

@media (min-width: 768px) {
  .gridFotos {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 3px;
  }

  .fotoSeccion {
    max-width: 100%;
    max-height: 100%;
    width: auto;
    height: auto;
  }

  .foto1 {
    grid-column: span 2;
  }
  
  .foto2 {
    grid-column: span 1;
  }
  
  .foto3 {
    grid-column: 2;
    grid-row: 2;
    
  }

  .foto4 {
    grid-row: 1 / 2;
    grid-column: 3;
  }

  .foto5 {
    grid-column: span 3; 
  }

  .foto6 {
    grid-row: 2;

    grid-column: 1;
  }

}
</style>
