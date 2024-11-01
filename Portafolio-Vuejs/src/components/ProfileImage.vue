<template>
    <div class="profile-container">
      <div class="loader-circle"></div>
      <img class="profile-image" :src="imageSrc" alt="Profile" />
    </div>
  </template>
  
  <script>
  export default {
    props: {
      imageSrc: {
        type: String,
        required: true
      }
    }
  };
  </script>
  
  <style scoped>
  .profile-container {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.loader-circle {
  width: 340px;
  height: 340px;
  border: 5px solid rgba(0, 0, 0, 0.1);
  border-top: 5px solid rgba(237,45,237,1);
  border-radius: 50%;
  animation: spin 9s linear infinite;
  margin-bottom: -160px; /* Alinea el círculo con la imagen */

}

.profile-image {
  width: 280px;
  height: 280px;
  border-radius: 50%;
  z-index: 10; /* Asegura que la imagen esté encima del círculo de carga */
  margin-top: -150px; /* Espacio entre el círculo y la imagen */
  margin-left: -5px ;

}

.container-lista {
  display: flex;
  justify-content: center;
  margin-top: 100px; /* Espacio entre la imagen y los iconos */
  list-style: none;
  padding: 0;
}

.icon-redsocial {
  margin: 0 10px; /* Espaciado entre los iconos */
}

  
  /* Animación de giro */
  @keyframes spin {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }


  </style>
  