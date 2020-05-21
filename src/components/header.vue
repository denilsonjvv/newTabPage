<template>
  <div id="wrapper-header">
      <div id="time">
        {{ horloge  }}
      </div>
      <div id="date">
        {{ date }}
      </div>
    <div id="weather">
      <img id="weather-icon"  v-bind:src="weatherIcon"  v-bind:alt="weatherIcon" />
      <div id="weather-temp">
        {{ weather.temperature }}
        30°C
      </div>

      <span id="weather-description">
        {{ weather.description }}
      </span>
    </div>
    <div id="kawaiiGif">
        <img id="gif" src="@/assets/gifKawaii.gif" alt="gifKawaii">
    </div>
  </div>

</template>

<script>
import moment from 'moment'
import axios from 'axios'

  export default{
    data: () => {
      return {
        horloge: null,
        date: null,
        weather: {
          description: null,
          icon: null,
          temperature: null,
          appID:'your API Key'
        }
      }
    },
    methods:{
      updateDateActuel(){
        this.horloge = moment().locale('us').format("MMMM Do YYYY")
      },
      updatehorlogeActuel(){
        this.date = moment().locale('us').format('h:mm:ss a')
      }
    },
    computed:{
      weatherIcon(){
        return require(`@/assets/weather/${this.weather.icon}.png`)
      },
    },
    created(){
        setInterval(() => this.updatehorlogeActuel(), 1000);
        setInterval(() => this.updateDateActuel(), 1000);
    },
    mounted () {
      axios
      .get(`https://api.openweathermap.org/data/2.5/weather?q=local&APPID=${this.weather.appID}`) // take care of that link, go to https://openweathermap.org/ and read their documentation for get your api ID and the good link for your local coordonates. 
      .then(response => (
        this.weather.icon = response.data.weather[0].icon,
        this.weather.temperature = Math.round(response.data.main.temp - 273.15),
        this.weather.description = response.data.weather[0].description
      ))
    },
  }
</script>
