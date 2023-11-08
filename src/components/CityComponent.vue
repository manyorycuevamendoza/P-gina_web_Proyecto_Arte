<script>
export default{
    name: "CityComponent",
    props: [
        "name",
        "country_name",
        "country_code",
        "state_name",
        "state_code",
        "latitude",
        "longitude",
],
};

</script>

<template>
    <div class="city">
        <h1>{{name}}</h1>
        <p>Country: {{country_name}}</p>
        <p>State: {{state_name}}</p>
        <p>Latitude: {{latitude}}</p>
        <p>Longitude: {{longitude}}</p>
        <img class="city-image" src="../assets/city.jpg" alt="city">


    </div>
</template>

<style scoped>
.city{
    padding: 2px;
    white-space: nowrap;
    width: 350px;
    height: 350px;
    border-style: solid;
    border-radius: 5px;
    border-color: grey;
}   
.city-image {
    width: 150px;  /* Cambia esto al ancho que desees */
    height: 150px; /* Cambia esto a la altura que desees */
    border-style: solid;
    border-radius: 5px;
    border-color: grey;
}

h1{
    overflow:hidden;
    text-overflow: ellipsis;
}



</style>
