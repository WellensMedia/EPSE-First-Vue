<template>
  <Header />
  <div class="content">
    <router-view></router-view>
  </div>
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.content {
  display: flex;
  height: calc(100vh - 91px);
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px 5vw;
}
h2 {
  color: rgb(66, 127, 181);
}
</style>
