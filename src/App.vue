<script>
import axios from 'axios';
export default {
  data() {
    return {
      city: "",
      error: "",
      info: null
    };
  },
  computed: {
    cityName() {
      return "«" + this.city + "»";
    }
  },
  methods: {
    getWeather() {
      if (this.city.trim(' ').length < 2) {
        this.error = "The city name must be more than one character.";
      }
      else {
        this.error = "";
        axios.get(`https://wttr.in/${this.city}&format=3`).then(x => this.info = x != null ? x : "Connection proplems");
      }
    }
  }
}
</script>

<template>
  <div class="wrap">
    <h1>Weather app</h1>
    <h3>You can find out the weather in {{ city == "" ? "your city" : cityName }}.</h3>
    <input type="text" placeholder="Enter your city" v-model="city" />
    <button v-if="city != ''" @click="getWeather()">Get the weather</button>
    <button disabled v-else>Get the weather</button>
    <p class="err">{{ error }}</p>
    <p>Info about weather in {{ city }}: </p>
    <p v-if="info != null">{{ info }}</p>
    <p v-else>Loading...</p>
  </div>
</template>

<style scoped>
.wrap {
  width: 900px;
  height: 500px;
  border-radius: 50px;
  padding: 20px;
  background: #1f0f24;
  text-align: center;
  color: rgb(255, 253, 216);
}

.wrap h1 {
  margin-top: 50px;
  font-family: Helvetica, Arial, Trebuchet, Tahoma, Verdana;
  font-weight: 100;
}

.wrap h3 {
  margin-top: 20px;
  font-family: Helvetica, Arial, Trebuchet, Tahoma, Verdana;
  font-weight: 100;
}

.wrap input {
  margin-top: 30px;
  background: transparent;
  border: 0px;
  border-bottom: 2px solid #110813;
  color: #fcfcfc;
  font-size: 14px;
  padding: 5px 8px;
  outline: none;
}

.wrap input:focus {
  border-bottom-color: #6e2d7d;
}

.wrap button {
  background: #e3bc4b;
  color: #fff;
  border-radius: 10px;
  border: 2px solid #b99935;
  padding: 10px 15px;
  margin-left: 20px;
  cursor: pointer;
  transition: transform 500ms ease;
}

.wrap button:disabled {
  background: #a78a33;
  cursor: not-allowed;
}

.wrap button:hover {
  transform: scale(1.1) translateY(-5px);
}

.wrap p {
  font-family: Helvetica, Arial, Trebuchet, Tahoma, Verdana;
  margin: 15px;
}

.wrap > .err {
  color: red;
}
</style>
