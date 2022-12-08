<template>
  <div class="header">
    <img class="logo" alt="Vue logo" src="../assets/logo.png" />
    <ul>
      <li><router-link to="/">Accueil</router-link></li>
      <li><router-link to="/services">Services</router-link></li>
      <li><router-link to="/projets">Projets</router-link></li>
      <li><router-link to="/contact">Contact</router-link></li>
    </ul>
    <ConnectWeb />
  </div>
</template>

<script>
import ConnectWeb from "./ConnectWeb.vue";

export default {
  name: "HeaderWeb",
  components: {
    ConnectWeb,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 60px;
  background: white;
  border-bottom: 1px solid grey;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.logo {
  height: 50px;
}
ul {
  display: flex;
  margin: 0;
  padding: 0;
  gap: 1rem;
  list-style: none;
}
li {
  padding: 0;
  margin: 0;
}
a {
  color: inherit;
  text-decoration: none;
}
</style>
