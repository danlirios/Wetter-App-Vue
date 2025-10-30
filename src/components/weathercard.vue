<script>
export default {
  props: {
    city: String,
    id: Number,
    myFunction: Function,
  },
  data() {
    return {
      temperature: null,
    };
  },

  async mounted() {
    console.log(this.city);
    const url = `https://api.weatherapi.com/v1/current.json?key=3e8306ca69624ad9b24134306252010&q=${this.city}`;
    const response = await fetch(url);
    const data = await response.json();
    console.log(data.current.temp_c);

    this.temperature = data.current.temp_c;

    //  this.temperature = data.current.temp_c
    // this.city = "";
  },
};
</script>

<template>
  <p v-if="temperature">
    The current temperature in {{ city }} is: {{ temperature }} °C
    <button @click="myFunction(this.id)">Delete</button>
  </p>
</template>
