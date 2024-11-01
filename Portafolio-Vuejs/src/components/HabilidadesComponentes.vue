<script setup>
import { ref } from 'vue';

// Lista de iconos de lenguajes de programación
const lenguajes = ref([
  { id: 1, src: '/src/components/icons/python-svgrepo-com.svg', alt: 'Python' },
  { id: 2, src: '/src/components/icons/java.svg', alt: 'Java' },
  { id: 3, src: '/src/components/icons/js.svg', alt: 'JavaScript' },
  { id: 4, src: '/src/components/icons/css.svg', alt: 'CSS' },
  { id: 5, src: '/src/components/icons/html.svg', alt: 'HTML' }
]);

// Lista de iconos de frameworks y librerías
const frameworks = ref([
  { id: 1, src: '/src/components/icons/bootstrap.svg', alt: 'Bootstrap' },
  { id: 2, src: '/src/components/icons/node.svg', alt: 'Node.js' },
  { id: 3, src: '/src/components/icons/react.svg', alt: 'React' },
  { id: 4, src: '/src/components/icons/vue.svg', alt: 'Vue.js' }
]);

// Lista de iconos de herramientas y software
const herramientas = ref([
  { id: 1, src: '/src/components/icons/git.svg', alt: 'Git' },
  { id: 2, src: '/src/components/icons/github.svg', alt: 'GitHub' },
  { id: 3, src: '/src/components/icons/sql.svg', alt: 'SQL' },
  { id: 4, src: '/src/components/icons/openai.svg', alt: 'Inteligencia Artificial' },
  { id: 5, src: '/src/components/icons/visual.svg', alt: 'Visual Studio Code' }
]);
</script>

<template>
  <div class="habilidades">
    <h1>Habilidades</h1>
    
    <h2>Lenguajes de Programación</h2>
    <div class="carousel lenguajes-carousel">
      <div class="carousel-track">
        <div v-for="lenguaje in lenguajes" :key="lenguaje.id" class="carousel-item">
          <img :src="lenguaje.src" :alt="lenguaje.alt" class="icon"/>
        </div>
        <!-- Duplicamos los ítems para crear el bucle infinito -->
        <div v-for="lenguaje in lenguajes" :key="'dup-' + lenguaje.id" class="carousel-item">
          <img :src="lenguaje.src" :alt="lenguaje.alt" class="icon"/>
        </div>
      </div>
    </div>
    
    <h2>Frameworks y Librerías</h2>
    <div class="carousel frameworks-carousel">
      <div class="carousel-track">
        <div v-for="framework in frameworks" :key="framework.id" class="carousel-item">
          <img :src="framework.src" :alt="framework.alt" class="icon"/>
        </div>
        <!-- Duplicamos los ítems para crear el bucle infinito -->
        <div v-for="framework in frameworks" :key="'dup-' + framework.id" class="carousel-item">
          <img :src="framework.src" :alt="framework.alt" class="icon"/>
        </div>
      </div>
    </div>
    
    <h2>Herramientas y Software</h2>
    <div class="carousel herramientas-carousel">
      <div class="carousel-track">
        <div v-for="herramienta in herramientas" :key="herramienta.id" class="carousel-item">
          <img :src="herramienta.src" :alt="herramienta.alt" class="icon"/>
        </div>
        <!-- Duplicamos los ítems para crear el bucle infinito -->
        <div v-for="herramienta in herramientas" :key="'dup-' + herramienta.id" class="carousel-item">
          <img :src="herramienta.src" :alt="herramienta.alt" class="icon"/>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.habilidades {
  text-align: center;
  padding: 20px;
}

.carousel {
  overflow: hidden;
  width: 100%;
  height: 100px; /* Ajusta la altura según necesites */
  margin: 20px 0;
}

.carousel-track {
  display: flex;
  width: max-content;
  animation: scroll 30s linear infinite;
}

.lenguajes-carousel .carousel-track {
  animation-direction: normal;
  background: linear-gradient(to right, #743ad5 0%, #d53a9d 100%);
}

.frameworks-carousel .carousel-track {
  animation-direction: reverse;
  background: linear-gradient(to left, #743ad5 0%, #d53a9d 100%);
}

.herramientas-carousel .carousel-track {
  animation-direction: normal;
  background: linear-gradient(to right, #743ad5 0%, #d53a9d 100%);
}

.carousel-item {
  flex: 0 0 auto;  /* Esto asegura que los íconos no se expandan más allá de su tamaño */
  min-width: 100px;  /* Asegura el tamaño mínimo del ícono */
  margin: 0 10px;  /* Margen entre los íconos */
  display: flex;  /* Añadido para centrar verticalmente los íconos dentro del carrusel */
  align-items: center;  /* Asegura que los íconos estén centrados verticalmente */
}

.icon {
  width: 50px;  /* Tamaño del ícono */
  height: 50px;  /* Tamaño del ícono */
}

@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

/* Barras deslizantes */
.habilidades h2 {
  position: relative;
  overflow: hidden;
}

.habilidades h2::before,
.habilidades h2::after {
  content: '';
  position: absolute;
  width: 100%;
  height: 5px;
  top: 95%;
  transform: translateY(-50%);
  background-color: rgba(0, 0, 0, 0.5);
}

.habilidades h2::before {
  left: -100%;
  animation: slideRight 10s linear infinite;
}

.habilidades h2::after {
  right: -100%;
  animation: slideLeft 10s linear infinite;
}

@keyframes slideRight {
  0% {
    left: -100%;
  }
  100% {
    left: 100%;
  }
}

@keyframes slideLeft {
  0% {
    right: -100%;
  }
  100% {
    right: 100%;
  }
}
</style>
