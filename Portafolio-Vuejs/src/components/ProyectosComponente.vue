<script setup>
import { ref } from 'vue';
import finalImage from '../assets/final.png';
import casapileImage from '../assets/casapile.jpg';
import inmobiliariaImage from '../assets/inmobiliaria.png';
import javaFrontImage from '../assets/javaFront.png';

const experiencias = ref([
  {
    id: 1,
    imageSrc: finalImage,
    titulo: 'Líder de Proyecto',
    descripcion: 'Fui líder de proyecto en la primera parte del curso de programación 2024. Video presentación del proyecto.',
    url: 'https://www.youtube.com/playlist?list=PLeO2T8e-S41jlMtu6rqjQf31r7TK0Pgrn'
  },
  {
    id: 2,
    imageSrc: casapileImage,
    titulo: 'Desarrollo Front-End',
    descripcion: 'Desarrollo del front para aprobar el curso de programación dictado por Egg Cooperation 2023.',
    url: 'https://github.com/maxiberosich/OpenHouse'
  },
  {
    id: 3,
    imageSrc: inmobiliariaImage,
    titulo: 'Inmobiliaria Estudio Quality',
    descripcion: 'Aún en desarrollo la página web de una inmobiliaria, basado en tendencia de estilos front.'
  },
  {
    id: 4,
    imageSrc: javaFrontImage,
    titulo: 'Trabajo cierre de año',
    descripcion: 'Creación del front desde Java para el examen de crear una app en equipo. Próximamente video de la presentación.',
    url: 'https://github.com/matthzc332/biblioteca-plus'
  }
]);
</script>

<template>
  <div>
    <section class="experience-section">
      <div class="cards-container">
        <a v-for="item in experiencias" :key="item.id" :href="item.url" target="_blank" rel="noopener noreferrer" class="card">
          <img :src="item.imageSrc" alt="experience image" class="card-image"/>
          <div class="card-content">
            <h3>{{ item.titulo }}</h3>
            <p>{{ item.descripcion }}</p>
          </div>
        </a>
      </div>
    </section>
  </div>
</template>

<style scoped>
.experience-section {
  padding: 20px;
}

.cards-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.card {
  border: 1px solid #e3e3e3;
  border-radius: 10px;
  overflow: hidden;
  transition: transform 0.3s ease;
  text-decoration: none; /* Asegurarse de que no haya subrayado en el texto del enlace */
  color: inherit; /* Mantener el color del texto */
}

.card:hover {
  transform: scale(1.05);
}

.card-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.card:hover .card-image {
  transform: scale(1.1);
}

.card-content {
  padding: 15px;
  background-color: #040404;
}

h3 {
  margin: 0 0 10px;
}

p {
  margin: 0;
}

/* Estilos Responsivos */
@media (max-width: 768px) {
  .cards-container {
    grid-template-columns: 1fr; /* Una columna para pantallas pequeñas */
  }

  .card {
    margin-bottom: 20px; /* Espacio entre tarjetas en pantallas pequeñas */
  }

  .card-image {
    height: 150px; /* Ajustar la altura de la imagen en pantallas pequeñas */
  }

  .card-content {
    padding: 10px; /* Ajustar el padding en pantallas pequeñas */
  }

  h3 {
    font-size: 1.5rem; /* Ajustar el tamaño del texto en pantallas pequeñas */
  }

  p {
    font-size: 0.875rem; /* Ajustar el tamaño del texto en pantallas pequeñas */
  }
}
</style>
