<template>
    <div id="main">
        <label for="zipcode">Zipcode: </label>
        <input type="number" name="zipcode" id="zipcode" ref="zip">
        <label for="celfahr"> Celsius or Fahrenheit: </label>
        <input type="text" name="celfahr" id="celfahr" ref="temp">
        <input type="submit" value="Submit" @click="Submit()">
    </div>
</template>

<script>
import axios from 'axios'

export default {
    name: "WeatherChecker",
    data() {
        return {
            weather: [],
            zip: document.getElementById("zipcode"),
            apiKey: "4dff01729e9befa932e3844c8ba1a3ab",
            api: "https://api.openweathermap.org/data/2.5/weather?zip=94040,us&appid=4dff01729e9befa932e3844c8ba1a3ab",
            brokenApi: "https://api.openweathermap.org/data/2.5/weather?zip=" + this.zip + ",us&appid=" + this.apiKey,
            temp: ""
        }
    },
    methods: {
        Submit() {
            this.zip = this.$refs.zip.value //grabs the value from the template above and each input references the vue code
            this.temp = this.$refs.temp.value // ^^^
            this.brokenApi = "https://api.openweathermap.org/data/2.5/weather?zip=" + this.zip + ",us&appid=" + this.apiKey
            console.log(this.brokenApi)
            axios //axios call using the broken api that requires user input for the api to work
                .get(this.brokenApi)
                .then((response) => {
                    this.weather = response.data;
                    console.log(response);
            });

            var second = document.createElement("div");
            second.document.createElement("h1");

        }
    }
}
</script>
