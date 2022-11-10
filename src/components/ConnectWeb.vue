<template>
  <div class="user login" v-if="!logged" @click="login=true">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Pro 6.2.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. --><path d="M224 256c70.7 0 128-57.3 128-128S294.7 0 224 0S96 57.3 96 128s57.3 128 128 128zm-45.7 48C79.8 304 0 383.8 0 482.3C0 498.7 13.3 512 29.7 512H418.3c16.4 0 29.7-13.3 29.7-29.7C448 383.8 368.2 304 269.7 304H178.3z"/></svg>
  </div>
  <div class="user login" v-if="logged">
    Bonjour Ludovic Wellens
    <div class="disconnect" @click="logged=false">Me déconnecter</div>
  </div>
  <div class="bgoverlay" v-if="login" @click="closeConnect"></div>
  <div class="overlay" v-if="login">
    <h2>Connexion</h2>
    <label>User</label>
    <input type="text" v-model="user" />
    <label>Pass</label>
    <input type="password" v-model="pass" />
    <p class="error" v-if="error">Mauvais utilisateur ou mot de passe</p>
    <button @click="connect">Connexion</button>
  </div>
</template>

<script>
export default {
  name: 'ConnectWeb',
  data(){
    return {
      login: false,
      user: "",
      pass: "",
      error: false,
      logged: false
    }
  },
  methods: {
    closeConnect(){
      this.login = false
      this.pass = ""
      this.error = false
    },
    connect(){
      if(this.user=="admin" && this.pass=="admin"){
        this.login = false
        this.logged = true
        this.error = false
        this.pass = ""
      }else{
        this.error = true
        this.pass = ""
      }
    }
  }
}
</script>

<style scoped>
.login{
  cursor: pointer;
}
svg{
  height: 30px;
}
.bgoverlay{
  position: fixed;
  left: 0;
  top: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0,0,0,0.3);
  cursor: zoom-out;
}
.overlay{
  position: fixed;
  top: 50%;
  left: 50%;
  z-index: 5000;
  width: 300px;
  height: 300px;
  transform: translate(-50%,-50%);
  display: flex;
  flex-direction: column;
  background: white;
  justify-content: center;
  gap: 0.5rem;
  padding: 1rem;
  box-shadow: 0px 0px 10px rgba(0,0,0,0.3);
}
input{
  padding: 0.5rem;
}
button{
  display: block;
  padding: 0.5rem;
  cursor: pointer;
}
.error{
  color: red;
}
</style>
