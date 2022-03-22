<template>
  <section id="contacto">
    <h1 class="titulo"> Contacto</h1>

    <div class="formLayout">

      <img src="./../assets/fotos/cata_cine.png" alt="" class="imagenContacto">

      <div class="hidden sm:block hr border-2"></div>

      <form ref="form" @submit.prevent="sendEmail" class="flex flex-col justify-center w-full">
        <label class="p-1 pl-3 " for="nombre"> Nombre </label>
        <input class="p-3 m-3" type="text" v-model="form.from_name.value" id="nombre" required name="from_name" placeholder="Nombre">
        <label class="p-1 pl-3 " for="mail"> E-Mail </label>
        <input class="p-3 m-3" type="email" v-model="form.reply_to.value" id="mail" required name="reply_to" placeholder="E-mail">
        <label class="p-1 pl-3 " for="mensaje"> Mensaje </label>
        <textarea class="p-3 m-3" v-model="form.message.value" id="mensaje" name="message" required cols="30" rows="10" placeholder="Mensaje"></textarea>

        <input type="submit" class="boton" :value="mensajeEnviado" :disabled="mensajeEnviado != '' " :class="{ negro: mensajeEnviado != ''}">

      </form>
    </div>
  </section>
</template>

<script setup>
  import emailjs from '@emailjs/browser';
  import { ref } from 'vue'

  const mensajeEnviado = ref('');

  const form = ref({
    from_name: '',
    reply_to: '',
    message: ''
  })

  function sendEmail() {
    console.log('ccscs', mensajeEnviado.value, form.value)
    if(mensajeEnviado.value == '') {
      mensajeEnviado.value = 'Enviando...'
      emailjs.sendForm('service_6l3q9yw', 'template_fu1pi0v', form.value, 'AKxffEEBf_2I64PJR')
      .then((result) => {
        mensajeEnviado.value = 'Mensaje enviado.'
        console.log(result)
      }, (error) => {
        mensajeEnviado.value = 'Error.'
        console.log('error')
      });
    }
  }
</script>

<style scoped>

form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
}

.formLayout {
  padding: 1rem;
}

.imagenContacto {
  max-width: 20vw;
  min-width: 256px;
  min-height: 256px;
  width: auto;
  height: auto;
  margin: auto;
  display: none;
}

.hr {
  display: none;
  border-left: #000000 1px solid;
  margin: 0 2rem;
}

input {
  height: 52px;
  background: #fff;
  color: #000;
  font-size: 14px;
  border-radius: 5px;
  margin-top: 1rem;
  margin-bottom: 1rem;
  -webkit-box-shadow: none!important;
  box-shadow: none!important;
  border: 1px solid #000000;
}

textarea {
  background: #fff;
  color: #000;
  margin-top: 1rem;
  margin-bottom: 1rem;
  font-size: 14px;
  border-radius: 5px;
  -webkit-box-shadow: none!important;
  box-shadow: none!important;
  border: 1px solid #000000;
  padding-top: 1rem;
}

input, textarea{
  color: #000000;
  font-size: 1rem;
  padding-left: 1rem;
}

::-webkit-input-placeholder {
  font-family: 'Montserrat', sans-serif;
}
:-moz-placeholder {
  font-family: 'Montserrat', sans-serif;
}
::-moz-placeholder {
  font-family: 'Montserrat', sans-serif;
}
:-ms-input-placeholder {
  font-family: 'Montserrat', sans-serif;
}

.boton:hover {
  cursor: pointer;
  transform: scale(1.1);  
}

.boton {
  border-radius: 20px;
  background-color: #000000;
  color: #fff;
  font-weight: 600;
  text-transform: uppercase;
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 17px;
  padding: 0.5rem 1rem;
  margin: auto;
  transition: 0.25s;
}

@media (min-width: 768px) {
  .hr {
    display: block;
  }

  .imagenContacto {
    display: block;
  }

  .formLayout {
    display: flex;
    padding: 2rem;
  }

}

</style>