<template>
  <main>
    <div class="weather">
  <header-item />
  <search-box :weather="weather" @getWeather="clickWeather" />
  <weather-info v-bind:weatherData='weatherData' />
  </div>
  
</main>
</template>
<script>


export default{

data() {
 return { 
    weatherData: [],
    errors:[],
    weather:'',
    API__KEY :'f10d459d04fcea9aa87124713863823c'
 }
},
methods:{
    clickWeather(weatherData){
      this.weatherData.push(weatherData)
    }
},
    // watch: {
    //     weatherData: {
    //         handler: function(newValue) {
    //             console.log(newValue)
                
    //         },
    //         deep: true
    //     }
    // }
//     computed: {
//   weat: function () {
//     return this.weatherData
//   }
// }
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
