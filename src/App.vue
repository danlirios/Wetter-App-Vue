<script>
import MyButton from "./components/MyButton.vue";
import weathercard from "./components/weathercard.vue";

export default {
  components: { MyButton, weathercard },
  data() {
    return {
      city: "",
      // temperature: null,
      cards: [],
      nextId: 1,
    };
  },
  methods: {
    addCity() {
      this.cards.push({
        id: this.nextId,
        city: this.city,
      });
      console.log(this.city);
      this.city = "";
      this.nextId++;
    },
    delBtn(id) {
      this.cards = this.cards.filter((item) => item.id !== id);
    },
  },
};
</script>

<template>
  <div id="app">
    <h1>Weather info 🌤️</h1>

    <div class="search-box">
      <input
        id="box"
        v-model="city"
        type="text"
        class="search-box"
        placeholder="Write a city"
      />
      <MyButton text="search" @click="addCity" />
      <!-- myFunction has the same function but different sintax-->
      <weathercard
        v-for="item in cards"
        :key="item.id"
        :id="item.id"
        :city="item.city"
        :myFunction="delBtn"
      />
      <!-- :myFunction="() => delBtn(item.id)" -->
    </div>
  </div>
</template>

<style>
body {
  background-image: url("./assets/weather.jpg");
}
#box {
  width: 200px;
  height: 35px;
}
p {
  color: black;
}
</style>

// api_key:
`http://api.weatherapi.com/v1/current.json?key=3e8306ca69624ad9b24134306252010&q=${city}`
