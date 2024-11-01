<template>
  <footer class="footer">
    <h1 class="contact">Escribeme!!!</h1>
    <ul class="menu">
      <li><a class="menu__link" href="#">Mc</a></li>
      <li><a class="menu__link" href="#educacion">Educación</a></li>
      <li><a class="menu__link" href="#proyectos">Proyectos</a></li>
      <li><a class="menu__link" href="#experiencia">Experiencia</a></li>
      <li><a class="float-wa" href="https://wa.me/5492604399605?text=Hola" target="_blank">
        <img src="../components/icons/whatsapp.svg" alt="WhatsApp" class="whatsapp-icon">
      </a></li>
    </ul>
    <p>&copy;2024 Matias Cabello | All Rights Reserved</p>
  </footer>
</template>

<script>
export default {
  name: 'FooterComponente'
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700;800;900&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}

body {
  display: flex;
  background: #333;
  justify-content: flex-end;
  align-items: flex-end;
  min-height: 100vh;
}

.footer {
  position: relative;
  width: 100%;
  background: #0f0c29;
  background: linear-gradient(to right, #24243e, #302b63, #0f0c29);
  min-height: 150px;
  padding: 20px 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  border-top: 5px solid #aa00ff;
  box-shadow: 0 0 10px #aa00ff, 0 0 20px #aa00ff, 0 0 30px #aa00ff, 0 0 40px #aa00ff;
}

.social-icon, .menu {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 10px 0;
  flex-wrap: wrap;
}

.social-icon__item, .menu__item {
  list-style: none;
}

.social-icon__link {
  font-size: 2rem;
  color: #fff;
  margin: 0 10px;
  display: inline-block;
  transition: 0.5s;
  text-shadow: 0 0 5px #00ffcc, 0 0 10px #00ffcc, 0 0 15px #00ffcc, 0 0 20px #00ffcc, 0 0 25px #00ffcc, 0 0 30px #00ffcc, 0 0 35px #00ffcc;
}

.social-icon__link:hover {
  transform: translateY(-10px);
}

.menu__link {
  font-size: 1.2rem;
  color: #fff;
  margin: 0 10px;
  display: inline-block;
  transition: 0.5s;
  text-decoration: none;
  opacity: 0.75;
  font-weight: 300;
  text-shadow: 0 0 5px #00ffcc, 0 0 10px #00ffcc, 0 0 15px #00ffcc, 0 0 20px #00ffcc, 0 0 25px #00ffcc, 0 0 30px #00ffcc, 0 0 35px #00ffcc;
}

.menu__link:hover {
  opacity: 1;
}

.footer p {
  color: #fff;
  margin: 15px 0 10px 0;
  font-size: 1rem;
  font-weight: 300;
  text-shadow: 0 0 5px #00ffcc, 0 0 10px #00ffcc, 0 0 15px #00ffcc, 0 0 20px #00ffcc, 0 0 25px #00ffcc, 0 0 30px #00ffcc, 0 0 35px #00ffcc;
}

.contact {
  color: #00ffcc;
  font-size: 2.5rem;
  text-shadow: 0 0 10px #00ffcc, 0 0 20px #00ffcc, 0 0 30px #00ffcc, 0 0 40px #00ffcc;
  margin-bottom: 20px;
}

.float-wa {
  position: fixed;
  width: 50px;
  height: 50px;
  bottom: 30px;
  right: 30px;
  background-color: #25d366;
  color: #FFF;
  border-radius: 50px;
  text-align: center;
  font-size: 30px;
  z-index: 100;
}

.whatsapp-icon {
  width: 100%;
  height: 100%;
}
</style>
