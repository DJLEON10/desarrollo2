<script setup>
import { ref } from 'vue';

let nombre =ref ('')
let apellido =ref ('')
let celular =ref ('')
let edad =ref ('')
let totalEdad = 0
let pasAño = 1000*60*60*24*365
let años = 0
function calEdad (){
  const timeActual = new Date()

  let timeage = new Date(edad.value)
   
  totalEdad = timeActual-timeage


años = parseInt(totalEdad/pasAño)


return años

}



</script>

<template>
  <section class="padre">
    <div class="titulo"><h1>EVENTOS LEON</h1></div>

    <div class="entradas">
      <input v-model="nombre" type="text" placeholder="escriba su nombre">
      <input v-model="apellido" type="text" placeholder="escriba su apellido">
      <input v-model="edad" type="date" >
      <input v-model="celular" type="tel" placeholder="escriba su numero de celular">
    </div>


   

  </section>
  <section class="targeta">
      <div class="titulo"><h1>EVENTOS LEON</h1></div>

      <div class="entradas">
        <div class="nombre"><h1>{{ nombre }}  {{ apellido }} </h1></div>
        <div class="numero"><h1>{{celular}}</h1></div>
        <div class="edad"><h1> {{calEdad (edad) }} </h1> <h1 v-if="(años<18)"> necesita acompañante </h1></div>

      </div>

    </section>
</template>

<style scoped>
.titulo{
background-color: brown;
display: flex;
justify-content: center;
padding: 15px;
}
.padre{
  background-color: aqua;
}
.entradas{
  display: grid;
  max-width: 1000px;
  margin: 15px auto;

}
input{
  padding: 8px;
}
.targeta{
  max-width: 1100px;
  margin: 0 auto;

}
.nombre{
  display: flex;
  justify-content: center;
}
.numero{
  display: flex;
  justify-content: center;
}
.edad{
  display: flex;
  justify-content: center;
}

</style>
