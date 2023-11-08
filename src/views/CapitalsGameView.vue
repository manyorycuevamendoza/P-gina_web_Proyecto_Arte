<script>
import countries from "/src/datasets/countries.json";
import CountryComponent from "../components/CountryComponent.vue";

export default {
  name: "CapitalsGameView",
  components: {
    CountryComponent,
  },
  data() {
    return {
      country: {},
      capital: "",
      puntaje: 0,
    };
  },
  created() {
    this.country = countries[Math.floor(Math.random() * countries.length)];
  },
  methods: {
    setCapital(e) {
      //: implementar. fija la capital del input.
      this.capital = e.target.value;

    },
    adivinarCapital() {
      //: implementar. verifica se la adivinanza es correcta.
      if (this.capital.toLowerCase() === this.country.capital.toLowerCase()) {
        this.puntaje++;
        this.country = countries[Math.floor(Math.random() * countries.length)];
        this.capital = "";
      } else {
        alert("Incorrecto");
      }


    },
  },
};
</script>

<template>
  <h1>Puntaje: {{ puntaje }}</h1>
  <div class="countries">
    <!-- : usar los metodos definidos arriba dentro del input para llenar el estado de la capital a adivinar-->

    
    <input
      placeholder="Adivina la capital"
      :value="this.capital"
      @input="setCapital"
    />
  
    <button @click="adivinarCapital">Adivina!</button>
    <div class="countries-container">
      <!--: CREAR EL COMPONENTE PARA VISUALIZAR EL PAIS-->
      <CountryComponent
        :name="country.name"
        :capital="'???'"
        :currency_name="country.currency_name"
        :currency="country.currency"
        :region="country.region"
        :code="country.iso2"
        :clickable="false"
      ></CountryComponent>
    </div>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
  .countries {
    align-items: center;
  }

  input {
    line-height: 2em;
  }

  .countries-container {
    margin-left: 35%;
    align-items: center;
    overflow-y: auto;
    vertical-align: middle;
    padding: 10px;
  }
}
</style>
