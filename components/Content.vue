<template>
    <div class="container">
        <div class="search">
            <div class="searchBar">T'es d'où toi ? <input type="text" placeholder="Limoge" v-on:keyup.enter="newCity" v-model="cityNew"></div>
            <div class="localisation">Parce qu'ici à <span>{{this.city}}</span> il fait seulement : </div>
        </div>
        <div class="meteo now"><Actuel v-if="meteo" :meteoToday="meteo[0]" /></div>
        <div class="meteo forecast">{{this.meteo[0]}}</div>
    </div>
</template>
    
<script>
import Actuel from './Actuel'
import Forecast from './Forecast'
import axios from 'axios'

var key = "672b44162a1bdad20cc23d34850b3530"

export default {


    methods: {
    },
    mounted: function() {
            axios.get(`https://api.openweathermap.org/data/2.5/forecast?q=${this.city},${this.code}&units=metric&appid=${key}`)
                .then(res => this.meteo = res.data.list)
                .catch(err => {});
    },
    data() {
        return {
            meteo : '',
            city: 'Nancy',
            code: 'fr',
            cityNew: ''
        }
    },
    methods: {
        newAPI: function(){
            axios.get(`https://api.openweathermap.org/data/2.5/forecast?q=${this.city},${this.code}&units=metric&appid=${key}`)
                .then(res => this.meteo = res.data.list)
                .catch(err => {});
        },

        newCity: function(){
            this.city = this.cityNew
            this.newAPI();
        }
    }
}
</script>

<style scoped>
.container {
    width: 100%;
    height: calc(100vh - 12rem);
    flex-flow: row wrap;
    align-items: center;
}

.meteo {
    height: 30vh;
    width: 100%;
}

.search {
    display: flex;
    flex-direction: row;
    align-items: center;
    flex-wrap: wrap;
}

.search .searchBar {
    width: 100%;
}

.search .localisation {
    width: 100%;
    padding-left: 2rem;
    line-height: 2.5rem;
}

.search .searchBar input {
    background-color: #1a1a1a;
    border: none;
    border-bottom: 1px solid #E1E1E1;
    color: #E1E1E1;
    height: 1.5rem;
    font-family: 'Secular One', sans-serif;
    font-size: 1rem;
}

.search .localisation span {
    color: #ea8685;
    font-family: 'Secular One', sans-serif;
    text-transform: lowercase;
    font-size: 2rem;
    text-decoration: underline;
}

</style>