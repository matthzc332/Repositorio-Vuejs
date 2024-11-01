<script setup>
import { ref } from 'vue';
import viaje from '../assets/mati.jpg';
import perros from '../assets/lililuna.jpg';
import esposa from '../assets/esposa.jpg';

const cards = ref([
  {
    id: 1,
    imageSrc: viaje,
    title: 'Viajero',
    description: 'Me encanta viajar y probar cosas diferentes. Cada destino es una nueva aventura, llena de experiencias únicas. Desde caminar por la playa de Rio de Janeiro hasta degustar sushi inspirado en la cocina nikkei en Caba.'
  },
  {
    id: 2,
    imageSrc: perros,
    title: 'Mis Perros',
    description: 'Disfruto el tiempo con mis fieles compañeros. No hay nada como una larga caminata por el parque al atardecer, o acurrucarse en el sofá con un buen libro y una taza de café caliente, mientras mis compañeros de cuatro patas descansan a mi lado.'
  },
  {
    id: 3,
    imageSrc: esposa,
    title: 'Mi Esposa',
    description: 'Compañera de aventuras, ella le da más sabor a mi vida. Originaria de Puerto Rico, su mundo de conocimientos ha abierto mis ojos al universo, con un enfoque diferente y divertido.'
  }
]);
</script>

<template>
  <div class="intereses">
    <div class="cards-container">
      <div v-for="card in cards" :key="card.id" class="card">
        <img :src="card.imageSrc" :alt="card.title" class="card__background"/>
        <div class="card__content">
          <div class="card__content--container flow">
            <h2 class="card__title">{{ card.title }}</h2>
            <p>{{ card.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
:root {
  --brand-color: hsl(46, 100%, 50%);
  --black: hsl(0, 0%, 0%);
  --white: hsl(0, 0%, 100%);
  --font-title: "Montserrat", sans-serif;
  --font-text: "Lato", sans-serif;
}

*, *::before, *::after {
  box-sizing: border-box;
}

body, h2, p {
  margin: 0;
}

body {
  display: grid;
  place-items: center;
  height: 100vh;
}

h1 {
  font-size: 2.5rem;
  font-family: var(--font-title);
  color: var(--white);
  margin-bottom: 2rem;
}

h2 {
  font-size: 2.25rem;
  font-family: var(--font-title);
  color: var(--white);
  line-height: 1.1;
}

p {
  font-family: var(--font-text);
  font-size: 1rem;
  line-height: 1.5;
  color: var(--white);
}

.flow > * + * {
  margin-top: var(--flow-space, 1em);
}

.cards-container {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.card {
  display: grid;
  place-items: center;
  width: 80vw;
  max-width: 21.875rem;
  height: auto; /* Ajuste para que el contenido se adapte */
  overflow: hidden;
  border-radius: 0.625rem;
  box-shadow: 0.25rem 0.25rem 0.5rem rgba(0, 0, 0, 0.25);
  margin-bottom: 2rem;
}

.card > * {
  grid-column: 1 / 2;
  grid-row: 1 / 2;
}

.card__background {
  object-fit: cover;
  width: 100%;
  height: 100%;
}

.card__content {
  --flow-space: 0.9375rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-self: flex-end;
  padding: 12% 1.25rem 1.875rem;
  background: linear-gradient(
    180deg,
    hsla(0, 0%, 0%, 0) 0%,
    hsla(0, 0%, 0%, 0.3) 10%,
    hsl(0, 0%, 0%) 100%
  );
}

.card__content--container {
  --flow-space: 1.25rem;
}

.card__title {
  position: relative;
  width: fit-content;
  width: -moz-fit-content;
}

.card__title::after {
  content: "";
  position: absolute;
  height: 0.3125rem;
  width: calc(100% + 1.25rem);
  bottom: calc((1.25rem - 0.5rem) * -1);
  left: -1.25rem;
  background-color: var(--brand-color);
}

@media (any-hover: hover) and (any-pointer: fine) {
  .card__content {
    transform: translateY(62%);
    transition: transform 500ms ease-out;
    transition-delay: 500ms;
  }

  .card__title::after {
    opacity: 0;
    transform: scaleX(0);
    transition: opacity 500ms ease-in, transform 500ms ease-out;
    transition-delay: 500ms;
    transform-origin: right;
  }

  .card__background {
    transition: transform 500ms ease-in;
  }

  .card__content--container > :not(.card__title) {
    opacity: 0;
    transition: transform 500ms ease-out, opacity 500ms ease-out;
  }

  .card:hover, .card:focus-within {
    transform: scale(1.05);
    transition: transform 500ms ease-in;
  }

  .card:hover .card__content, .card:focus-within .card__content {
    transform: translateY(0);
    transition: transform 500ms ease-in;
  }

  .card:focus-within .card__content {
    transition-duration: 0ms;
  }

  .card:hover .card__background, .card:focus-within .card__background {
    transform: scale(1.3);
  }

  .card:hover .card__content--container > :not(.card__title), .card:focus-within .card__content--container > :not(.card__title) {
    opacity: 1;
    transition: opacity 500ms ease-in;
    transition-delay: 500ms;
  }

  .card:hover .card__title::after, .card:focus-within .card__title::after {
    opacity: 1;
    transform: scaleX(1);
    transform-origin: left;
    transition: opacity 500ms ease-in, transform 500ms ease-in;
    transition-delay: 500ms;
  }
}
</style>
