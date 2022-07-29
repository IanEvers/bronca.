<script>

</script>

<template>

<header>
  
  <nav>
    <a href="#proyectos"> Proyectos </a>
    <a href="#fotos"> Fotos </a>
    <a href="#contacto"> Contacto </a>
  </nav>
  
</header>

</template>

<style scoped>

a {
  color: #120a1f;
  text-decoration: none;
}

header {
  border-bottom: #120a1f solid 1px;
  border-top: #120a1f solid 1px;
  margin-top: 2rem;
  background-color: white;
  position: sticky;
  top: 0;
  z-index: 100;
}

nav {
  padding: 1rem;
  display: flex;
  justify-content: space-evenly;
  gap: 1rem;
}

@media (min-width: 640px) {
 

  nav {
    justify-content: flex-end;
    margin-right: 2rem;
  }
}

@media (min-width: 915px) {
   header {
    margin-top: 0rem;
  }
}

</style>
