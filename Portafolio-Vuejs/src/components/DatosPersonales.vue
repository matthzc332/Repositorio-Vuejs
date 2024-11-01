<template>
  <section class="profile-section">
    <div class="personal-info">
      <h4>Hi, I'm</h4>
      <h1>{{ title }}</h1>
      <h2>{{ descripcion }}</h2>
      <p>{{ presentacion }}</p>
      <br>
      <h3>Teléfono personal: {{ telefono }}</h3>
      <h4>{{ residencia }}</h4>
    </div>
    <div class="profile-container">
      <div class="loader-circle"></div>
      <ProfileImage :imageSrc="perfilImg" />
      <ul class="container-lista">
        <li v-for="red in redesSociales" :key="red.id">
          <a :href="red.url"
             target="_blank"
             rel="noopener noreferrer"
             :download="red.name === 'curriculum' ? 'CVMatiasCabello.pdf' : false">
            <img class="icon-redsocial" :src="red.src" width="35rem" :alt="red.name">
          </a>
        </li>
      </ul>
    </div>
  </section>
</template>

<script setup>
import ProfileImage from './ProfileImage.vue';

const title = 'Matias Cabello.';
const descripcion = 'Estudiante en la Tecnicatura Universitaria en Programación - UTN';
const presentacion = 'Mi pasión por el diseño viene de mi curiosidad constante y mi deseo de crear experiencias memorables. Me gusta el arte, viajar, los perritos y la pizza.';
const residencia = 'San Rafael, Mendoza, Argentina';
const telefono = '+54 9 2604-399605';

const redesSociales = [
  { id: 1, name: 'Linkedin', src: '/src/assets/linkedin_icon.svg', url: 'https://www.linkedin.com/in/matias-cabello-36b1981b2' },
  { id: 2, name: 'Instagram', src: '/src/assets/instagram_icon.svg', url: 'https://www.instagram.com/matthz.c332/?igsh=dGQ4aGdjNHRybzNn' },
  { id: 3, name: 'GitHub', src: '/src/assets/github_icon.svg', url: 'https://github.com/matthzc332' },
  { id: 4, name: 'curriculum', src: '/src/assets/cv_resume_icon.svg', url: '/src/assets/CVMatiasCabello.pdf' }
];

import perfilImg from '@/assets/perfil.jpg';
</script>

<style scoped>
.profile-section {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  padding: 20px;
  padding-top: 80px;
}

.personal-info {
  max-width: 60%;
  flex: 1 1 300px;
  margin-bottom: 20px;
}

.icon-redsocial {
  margin: 0 8px; /* Espaciado entre los iconos */
}

.profile-container {
  display: flex;
  flex-direction: column;
  align-items: center; /* Centra la imagen y los iconos */
  margin-left: 30px;
  flex: 1 1 300px;
}

.personal-info h1 {
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  font-size: 60px;
  width: 100%; /* Ajuste para evitar movimiento en móviles */
  white-space: nowrap;
  overflow: hidden;
  animation: typing 2s steps(21, end), blink-caret .5s step-end infinite alternate;
}

.personal-info h2 {
  font-size: 30px;
}

.container-lista {
  display: flex;
  flex-wrap: wrap;
  justify-content: center; /* Centra los iconos */
  align-items: center; /* Alinea verticalmente los iconos */
  margin-top: 40px; /* Ajusta el espacio entre la imagen y los iconos */
  padding: 10px;
  list-style: none;
}

/* Definir la animación estándar */
@keyframes typing {
  from {
    width: 0;
  }
  to {
    width: 12ch; /* Ajuste para mantener el ancho fijo después de la animación */
  }
}

@keyframes blink-caret {
  50% {
    border-color: transparent;
  }
}

/* Estilos Responsivos */
@media (max-width: 768px) {
  .profile-section {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .personal-info {
    max-width: 100%;
    margin-bottom: 20px;
  }

  .profile-container {
    margin-left: 0;
  }

  .personal-info h1 {
    font-size: 40px;
  }

  .personal-info h2 {
    font-size: 24px;
  }

  .container-lista {
    justify-content: space-evenly;
  }
}
</style>
