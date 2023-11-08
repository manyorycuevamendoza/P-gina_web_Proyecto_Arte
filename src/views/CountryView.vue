<script>
import countries from "/src/datasets/countries.json";

export default {
  name: "CountryView",
  data() {
    return {
      country: null, // Inicializar como null
    };
  },
  created() {
    // Encontrar el país solo si existe
    const countryCode = this.$route.params.code;
    if (countryCode) {
      this.country = countries.find(
        (country) => country.iso2 === countryCode.toUpperCase()
      );
    }
    // Si no existe, redirigir al usuario a la página de países
    if (!this.country) {
      this.$router.push("/countries");
    }


  },
};
</script>

<template>
  <div class="country">
    <!-- Verificar si country existe antes de mostrar sus propiedades -->
    <h1 v-if="country">{{ country.name }}</h1>
    <p v-if="country">Capital: {{ country.capital }}</p>
    <p v-if="country">Moneda: {{ country.currency_name }} ({{ country.currency}})</p>
    <p v-if="country">Región: {{ country.region }}</p>

    <!-- Cargar la bandera del país si country existe -->
    <img v-if="country" :src="`https://www.countryflagsapi.com/${country.iso2}.png`" alt="Bandera del país" />

    <div class="traducciones" v-if="country">
      <h2>Traducciones</h2>
      <h3
        v-for="(translation, index) in Object.keys(country.translations)"
        :key="index"
      >
        {{ `${translation}: ${country.translations[translation]}` }}
      </h3>
    </div>
  </div>
</template>

<style scoped>
.country {
  font-size: large;
}

.traducciones {
  color: white;
  display: grid;
}
</style>
