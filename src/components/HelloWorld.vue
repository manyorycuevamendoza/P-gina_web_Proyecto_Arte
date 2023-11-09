<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h3>
      "Barranco Deconstruido", es una exploración del arte callejero en el distrito de Barranco, ubicado en Lima, Perú. Barranco es conocido por su vibrante vida cultural y artística, siendo un punto de encuentro para artistas y amantes del arte, y un espacio donde la creatividad se manifiesta en cada esquina.
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -150px;
}

h3 {
  font-size: 1.2rem;
  color: rgb(242, 241, 243);
}

.greetings h1,
.greetings h3 {
  top: -150px;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
