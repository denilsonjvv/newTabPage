<template id="template-header">
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
        {{ weather.temperature }}°C
      </div>

      <span id="weather-description">
        {{ weather.description }}
      </span>
    </div>
    <div id="kawaiiGif">
        <img id="gif" src="@/assets/gifKawaii.gif" alt="gifKawaii">
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

<style lang="scss" scoped>
#wrapper-header{
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  grid-template-rows: repeat(2, 1fr);
  grid-gap: 0;
  // grid-template-columns: 40% 30% 30%;
  // grid-template-rows: 30% 30% 40%;

  // justify-items: stretch;
}
  #time{
    color: white;
    font-weight: 1000;
    font-size: 1.8rem;
    font-variant: small-caps;
    padding: 0.8em 0.2em 0 0.2em;
    align-self: stretch;
    margin: auto;
    grid-column: 1 / 6;
    grid-row: 1 / 2;
  }
    #date{
      color: white;
      font-weight: 1000;
      font-size: 1.5rem;
      font-variant: small-caps;
      padding: 0.5em 0.2em 0 0.2em;
      grid-column: 1 / 6;
      grid-row: 2 / 3;
    }
    #weather{
      grid-column: 6 / 9;
      grid-row: 1 / 3;
      #weather-icon{
        filter: invert(100%);
        width: 5rem;
        padding-top: 1.3rem;
        float: left;
      }
      #weather-temp{
        color: white;
        font-weight: 1000;
        font-size: 3rem;
        font-variant: small-caps;
        padding-top:1.3rem;
      }
      #weather-description{
        color: white;
        font-weight: 1000;
        font-size: 1.5rem;
        font-variant: small-caps;
        align-self: stretch;
      }
    }
      #kawaiiGif{
        grid-column: 9 / 13;
        grid-row: 1 / 3;
        #gif{
          width: 100px;
          overflow: hidden;
          padding-top: 20px;
        }
      }
</style>
