<script>
 export default {
    data() {
      return {
        // api_key: `http://api.weatherapi.com/v1/current.json?key=3e8306ca69624ad9b24134306252010&q=${city}`
    
      };
    },
    methods: {

    }
  }
</script>


<template>
  <h1>Weather info 🌤️</h1>
  <div id="app">
    <main>
      <div class="searh-box">
        <input type="text" class="search-box" placeholder="Write a city">
        <button id="getWeatherBtn">Search</button>
      </div>
    </main>
    
  </div>
  
</template>

<style scoped>
#app {
  background-image: url();
  background-size: cover;
}

</style>
