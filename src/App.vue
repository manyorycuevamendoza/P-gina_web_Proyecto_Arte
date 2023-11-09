<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";



</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="@/assets/gatito2.gif"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <HelloWorld msg="Gran Museo, Barranco Deconstruido" />

      <nav>
        <RouterLink to="/">Descripción</RouterLink>
        <RouterLink to="/countries">Museo</RouterLink>
        <RouterLink to="/cities">Vista General</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}



nav {
  width: 100%;
  font-size: 3px;
  text-align: center;
  margin-top: 0rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  
}

nav a:first-of-type {
  
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
    margin-top: 40px;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    top: -400px;
  }
}
</style>
