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

      <section id="proyectos">
        <h1 class="titulo"> Proyectos </h1>
      </section>

      <section id="fotos">
        <h1 class="titulo"> Fotos </h1>
      </section>

      <section id="contacto">
        <h1 class="titulo"> Contacto </h1>
      </section>

    </div>

    <a href="#home" class="backTop"> Inicio </a>

  </div>
</template>


<script setup>
import Header from "./components/Header.vue";

// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/script-setup-2/active-rfcs/0000-script-setup.md
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

.backTop {
  position: sticky;
  bottom: 20px;      
  margin-right:30px; 
  left: 85vw;
  margin-top: calc(100vh + 100px);
  
  /* visual styling */
  text-decoration: none;
  padding: 15px;
  font-family: sans-serif;
  color: #fff;
  background: #000;
  border-radius: 100px;
  white-space: nowrap;
}

section {
  min-height: 100vh;
  padding: 1rem;
  max-width: 1024px;
  margin: auto;
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

</style>
