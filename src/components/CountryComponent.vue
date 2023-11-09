

<template>
  <!--: Utilizar la propiedad creada para controlar el click. Cuando el componente es "clickeable", redirigir a la pagina del pais.
  Mira las rutas para ver como redirigir al usuario.-->
    <div class="country" :class="{ 'country-hover': clickable }" @click="clickable ? $router.push(`/countries/${code}`) : null">
  <!--: Poblar el HTML con las propiedades. Usar https://countryflagsapi.com/png/${code}-->

    <h1>{{ name }}</h1>
    <p>Capital: {{ capital }}</p>
    <p>Moneda: {{ currency_name }} ({{ currency}})</p>
    <p>Región: {{ region }}</p>
    <img src="city.jpg" class="country-image" />
    
  </div>

</template>


<script>
export default {
  name: "CountryComponent",
  props: [
    "name",
    "capital",
    "currency_name",
    "currency",
    "region",
    "code",
    //: crear una propiedad para determinar si al componente se le puede hacer click
    //la propiedad debe llamarse "clickable" y debe ser booleana
    "clickable",
  ],
};
</script>

<style scoped>
.country {
  padding: 1px;
  
  width: 350px;
  height: 350px;
  border-style: solid;
  border-radius: 5px;
  border-color: grey;
}

.country-hover:hover {
  background-color: rgb(49, 49, 49);
  cursor: pointer;
}
.country-image{
  width: 150px;  /* Cambia esto al ancho que desees */
  height: 150px; /* Cambia esto a la altura que desees */
  border-style: solid;
  border-radius: 5px;
  border-color: grey;
}

h1 {
  overflow: hidden;
  text-overflow: ellipsis;
}


</style>