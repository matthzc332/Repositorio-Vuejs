<template>
  <nav class="navbar" :class="{ 'navbar-scrolled': isScrolled }">
    <div class="navbar-brand">
      <a href="DatosPersonales" class="navbar-name">Mc</a>
    </div>
    <div class="navbar-toggle" @click="toggleMenu">
      ☰
    </div>
    <div class="navbar-menu" :class="{ 'navbar-menu-visible': isMenuVisible }">
      <ul class="navbar-list">
        <li v-for="nav in navegacion" :key="nav.nombre" class="nav-item">
          <a :href="nav.enlace">{{ nav.nombre }}</a>
        </li>
      </ul>
    </div>
  </nav>
  <div class="seperator-wrapper">
    <div class="seperator gradient"></div>
  </div>
  <div class="content">
    <!-- Tu contenido aquí -->
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const navegacion = ref([
  { id: 2, nombre: 'Educacion', enlace: '#educacion' },
  { id: 3, nombre: 'Proyectos', enlace: '#proyectos' },
  { id: 4, nombre: 'Experiencia', enlace: '#experiencia' },
  { id: 5, nombre: 'Habilidades', enlace: '#habilidades' }
]);

const isScrolled = ref(false);
const isMenuVisible = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;
};

const toggleMenu = () => {
  isMenuVisible.value = !isMenuVisible.value;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  list-style: none;
  background: linear-gradient(90deg, #0a0a0a, #1a1a1a, #2a2a2a);
  padding: 10px;
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  transition: background 0.3s ease, padding 0.3s ease;
  z-index: 1000;
}

.navbar-scrolled {
  background: rgba(0, 0, 0, 0.5);
  padding: 5px 10px;
}

.navbar-brand {
  margin-right: 20px;
}

.navbar-name {
  color: white;
  text-decoration: none;
  font-size: 24px;
  font-weight: bold;
}

.navbar-toggle {
  display: none;
  background: none;
  border: none;
  color: white;
  font-size: 24px;
}

.navbar-menu {
  display: flex;
  flex-grow: 1;
}

.navbar-menu-visible {
  display: block;
}

.navbar-list {
  display: flex;
  margin-left: auto;
}

.nav-item {
  color: white;
  text-decoration: none;
  margin: 0 15px;
  position: relative;
  transition: color 0.3s ease;
}

.nav-item a {
  color: white;
  text-decoration: none;
}

.nav-item::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -2px;
  left: 0;
  background-color: white;
  transition: width 0.3s ease;
}

.nav-item:hover {
  color: #FFD700;
}

.nav-item:hover::after {
  width: 100%;
}

body {
  width: 100%;
  height: 100%;
  overflow: auto;
  background: #111;
  padding-top: 60px;
}

.seperator-wrapper {
  width: 100%;
}

@media (max-width: 768px) {
  .navbar {
    flex-direction: column;
    align-items: flex-start;
    padding: 10px 20px;
  }

  .navbar-toggle {
    display: block;
  }

  .navbar-menu {
    display: none;
    width: 100%;
    flex-direction: column;
  }

  .navbar-list {
    flex-direction: column;
    width: 100%;
    margin: 0;
  }

  .nav-item {
    margin: 10px 0;
    width: 100%;
    text-align: left;
  }

  .navbar-menu-visible {
    display: flex;
  }
}

@keyframes rotate {
  from {
    background-position: -3000px;
  }
  to {
    background-position: 0px;
  }
}
</style>
