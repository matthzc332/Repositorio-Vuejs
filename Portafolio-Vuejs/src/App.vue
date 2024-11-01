<script setup>
import NavBar from './components/NavBar.vue';
import DatosPersonales from './components/DatosPersonales.vue';
import Educacion from './components/EducacionComponente.vue';
import ProyectosComponente from './components/ProyectosComponente.vue';
import ExperienciaComponente from './components/ExperienciaComponente.vue';
import HabilidadesComponentes from './components/HabilidadesComponentes.vue';
import InteresesComponentes from './components/InteresesComponentes.vue';
import FooterComponente from './components/FooterComponente.vue';
</script>

<template>
 <header>
  <!--Barra de navegacion-->
 <NavBar/>
 <!-- Componente Datos Personales -->
  <DatosPersonales/>
 </header>
 <main>
  
  <section id="experiencia"><h2>Experiencia</h2></section>
  <ExperienciaComponente/>
  <section id="proyectos"><h2>Proyectos</h2></section>
  <ProyectosComponente/>
  <section id="educacion"><h2>Educación</h2></section>
  <Educacion/>
  <section id="habilidades"><h2>Habilidades</h2></section>
  <HabilidadesComponentes/>
  <section id="intereses"><h2>Sobre mí</h2></section>
  <InteresesComponentes/>
  <section id="Footer"></section>
  <FooterComponente/>
 </main>
</template>

<style scoped>

</style>
