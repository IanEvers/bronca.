<script>

</script>

<template>

<header>
  
  <nav>
    <a href="#inicio"> Inicio </a>
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
  border-bottom: #120a1f solid 5px;
}

nav {
  padding: 1rem;
  display: flex;
  justify-content: center;
  gap: 1rem;
}

@media (min-width: 640px) {
  nav {
    justify-content: flex-end;
    margin-right: 2rem;

  }
}

</style>
