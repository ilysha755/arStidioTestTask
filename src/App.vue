<template>
  <main>
    <div class="weather">
  <header-item />
  <search-box :weather="weather" @weatherClick="getWeather"/>
  <weather-info  :weatherData="weatherData"/>
  </div>
  
</main>
</template>
<script>


export default{

data() {
 return {
    weatherData:null,
    weather:'',
 }
},
methods:{
  getWeather(weatherData) {
    this.weatherData = weatherData
  }
},

}
</script>
<style>
  *{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: 'Montserrat', sans-serif;
  }
  main{
      width: 100%;
  }
  .weather {
    max-width: 1200px;
    width: 100%;
    margin: 0 auto;
}
</style>
