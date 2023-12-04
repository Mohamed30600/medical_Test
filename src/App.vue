<script setup>
import CapteurVue from "./components/CapteurVue.vue";
</script>

<template>
  <header class="bg-primary text-white p-3">
    <div class="row">
      <div class="col-3">
        <img src="./assets/Logo.png" alt="Logo " class="tailleImage" />
      </div>
      <div class="col-8">
        <h1 class="text-center">
          Interface visuelle pour saisir l'index de santé afin de simuler dans
          quel service le patient doit etre rediriger
        </h1>
      </div>
    </div>
  </header>
  <body>
    <CapteurVue />
  </body>

  <RouterView />
</template>

<style scoped>
.tailleImage {
  width: 8em;
  background-color: red;
}
</style>
