<template>
  <nav v-if="isLogged">
    <img
      src="../assets/logos/icon-above-font.png"
      alt="Logo de la société Groupomania"
    />
    <router-link to="/">Accueil</router-link> |
    <router-link to="/profil">Profil</router-link> |
    <router-link to="/login">Déconnexion</router-link>
  </nav>
  <nav v-else id="imgLogin">
      <img
        src="../assets/logos/icon-above-font.png"
        alt="Logo de la société Groupomania"
      />
  </nav>
</template>
<script>
export default {
  name: "NavComponent",
  // Fonction pour la récupération du token
  data: () => ({
    isLogged: localStorage.getItem("token"),
  }),
  // Fonction pour la mise à jour du token
  updated() {
    this.isLogged = localStorage.getItem("token");
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
nav {
  padding: 30px;
  min-width: 80%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  img {
    max-height: 110px;
    max-width: 110px;
    float: left;
  }
  h2 {
    display: flex;
    align-items: center;
    align-self: center;
  }
  a {
    font-weight: bold;
    color: #2c3e50;
    text-decoration: none;
    &:hover {
      color: #42b983;
    }
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
#imgLogin {
  display: flex;
  justify-content: center;
  & img {
    min-width: 300px;
    min-height: 300px;
  }
}
</style>