<script setup>
import { ref } from 'vue';

const arreglo = ref([
  { id: 1, fecha: '2024', titulo: 'Comienzo estudios en programacion en la UTN', descripcion: 'Estudio en Curso' },
  { id: 2, fecha: '2023', titulo: 'Culmino estudio programador Full Stack en Egg', descripcion: 'Carga horaria 441hs teoricas practicas' },
  { id: 3, fecha: '2022', titulo: 'Comienzo estudios en Egg Cooperation', descripcion: 'Argentina programa' },
  { id: 4, fecha: '2020', titulo: 'Diplomatura en Marketing en U. Blas Pascal', descripcion: 'Carga horaria 200hs ' }
]);
</script>

<template>
  <h1>Línea de Tiempo</h1>
  <div class="timeline">
    <p v-for="item in arreglo" :key="item.id">
      <strong>{{ item.fecha }}</strong><br>
      <strong>{{ item.titulo }}</strong><br>
      {{ item.descripcion }}
    </p>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Open+Sans:400,400i,700");

body {
  font-family: 'Open Sans', sans-serif;
  margin: 0;
  padding: 0 4em;
}

.timeline {
  min-width: 300px;
  max-width: 500px;
  margin: auto;
}

p {
  font-size: 1em;
  line-height: 1.75em;
  border-top: 3px solid;
  border-image: linear-gradient(to right, #743ad5 0%, #d53a9d 100%);
  border-image-slice: 1;
  border-width: 3px;
  margin: 0;
  padding: 40px;
  counter-increment: section;
  position: relative;
  color: #ffffff;

  /* Números */
  &:before {
    
    position: absolute;
    border-radius: 50%;
    padding: 10px;
    height: 1.25em;
    width: 1.25em;
    background-color: #a0a8b7;
    text-align: center;
    line-height: 1.25em;
    color: #f3f2f2;
    font-size: 1em;
    top: 50%;
    transform: translateY(-50%);
  }
}

/* Bordes para números impares */
p:nth-child(odd) {
  border-right: 3px solid;
  padding-left: 0;

  &:before {
    left: 100%;
    margin-left: -20px;
  }
}

/* Bordes para números pares */
p:nth-child(even) {
  border-left: 3px solid;
  padding-right: 0;

  &:before {
    right: 100%;
    margin-right: -20px;
  }
}

/* Manejar el primer y último elemento */
p:first-child {
  border-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}

p:last-child {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
</style>
