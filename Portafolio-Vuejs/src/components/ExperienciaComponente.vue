<script setup>
</script>

<template>
  <section class="experience-section">
    <div class="experience-box">
      <p>“Soy un desarrollador con experiencia en liderazgo de proyectos y desarrollo front-end.
         Mi trayectoria incluye trabajos en equipos multidisciplinarios, creando soluciones innovadoras y efectivas.
          Además, he desarrollado habilidades blandas en atención al público y gestión de propiedades, que me permiten comunicarme eficazmente,
           resolver problemas y brindar un excelente servicio al cliente.”</p>
    </div>
  </section>
</template>

<style scoped>
.experience-section {
  padding: 20px;
}

.experience-box {
  border: 2px solid #ccc;
  border-radius: 10px;
  padding: 20px;
  margin-top: 20px;
  position: relative;
  animation: borderGlow 2s infinite;
}

@keyframes borderGlow {
  0% {
    border-color: #8e44ad;
  }
  50% {
    border-color: #f39c12;
  }
  100% {
    border-color: #8e44ad;
  }
}

h2 {
  text-align: center;
  font-size: 24px;
  margin-bottom: 20px;
}

p {
  font-size: 16px;
  line-height: 1.6;
}
</style>
