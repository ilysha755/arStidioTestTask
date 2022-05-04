<template>
                <div class="weather__search">
                <input type="text" placeholder="Найти погоду" v-model="weather" @keyup.enter="clickWeather" >
                <button @click="clickWeather">Найти погоду</button>
            </div>
</template>
<script>
import axios from 'axios'
export default {
   name:'search-box' ,

   data(){
       return{
           weather:'',
           API__KEY :'f10d459d04fcea9aa87124713863823c',
         }
   },
   methods:{
    async clickWeather() {
    axios.get('https://api.openweathermap.org/data/2.5/weather?q='+ this.weather +'&appid='+ this.API__KEY +'&units=metric&lang=ru')
    .then(response => {
    this.weatherData = response.data
    this.$emit('getWeather', this.weatherData)
    console.log(response.data)
    })
    .catch(e => {
      console.log(e)
    })
    this.weather=""
  },
   },
}
</script>
<style lang="scss" scoped>
.weather__search {
    width: 100%;
    display: flex;
    margin-top: 50px;
    input{
        width: 100%;
        height: 45px;
        border: none;
        background-color: #ededed;
    }
    button{
        max-width: 150px;
        width: 100%;
        border: none;
        border-radius:0px 0px 20px 0px;
    }
}
</style>