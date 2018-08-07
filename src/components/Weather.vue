<template>
  <section class="weather-card">
    <span class="weather-card__city">{{ items.name }}</span>

    <div class="weather-icon__container">
    </div>

    <div class="weather-temperature__container">
        <span class="weather-temperature__text">{{ items.main.temp }}</span>
        <span class="weather-temperature__metric"></span>
        <span class="weather-temperature__condition">{{ items.weather[0].description }}</span>
    </div>

    <section class="weather-maxmin__container">
        <div class="weather-min__container">
            <svg class="min-arrow__icon" viewBox="188.5 807 21 21">
                <path d="M209.5 817.5h-21L199 828z" data-name="Min Arrow" fill="#00ff9b"></path>
            </svg>

            <span class="min-temperature__text">{{ items.main.temp_min }}</span>
            <span class="min__text">Min</span>
        </div>

        <div class="max__container">
            <svg class="max-arrow__icon" viewBox="449.5 820 21 21">
                <path d="M449.5 830.5h21L460 820z" data-name="Max Arrow" fill="red"></path>
            </svg>

            <span class="max-temperature__text">{{ items.main.temp_max }}</span>
            <span class="max__text">Max</span>
        </div>
    </section>
  </section> 
</template>

<script>
import axios from 'axios'

export default {
    name: 'Weather',
    props: {
        msg: String
    },

    data() {
        return {
            items: []
        }
    },

    mounted() {
        this.fetchItems()
    },

    methods: {
        fetchItems() {
            const API = 'https://api.openweathermap.org/data/2.5/weather?q=Belo+Horizonte&units=metric&APPID=6a6ee399b712f32feed7e00d2d202715&lang=pt';

            axios
            .get(API)
            .then(response => {
                console.log(response.data)
                this.items = response.data
            })
            .catch(error => {
                console.log(error)
                this.errored = true
            })
        }
    }
}
</script>

<style scoped>
 .weather-card {
    animation: 1.25s ease-in-out fadein;
    background: linear-gradient(180deg, rgba(2,0,36,1) 0%, rgba(9,9,121,1) 35%, rgba(0,212,255,1) 100%);
    box-shadow: 0 0 2rem rgba(0,0,255,.1);
    border-radius: 1.75rem;
    color: #fff;
    cursor: pointer;
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    justify-items: center;
    height: 30rem;
    margin: 2rem;
    padding: 2rem;
    width: 19rem;
}

.weather-card__city {
    text-transform: uppercase;
    letter-spacing: 1px;
    font-size: 1.8rem;
}
</style>