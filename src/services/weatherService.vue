<script>
  export class WeatherService {
    getCityWeatherByName(city, metric: 'metric' | 'imperial' = 'metric') {
      const API = 'https://api.openweathermap.org/data/2.5/weather?q=${city}&units=${metric}&APPID=6a6ee399b712f32feed7e00d2d202715&lang=pt';

      axios
        .get(API)
        .then(response => {
          this.items = response.data
        })
        .catch(error => {
          this.errored = true
        })
    },

    getCitiesWeatherByName() {}
    getWeatherState() {}
    getCurrentTemp() {}
    getCurrentHum() {}
    getCurrentWind() {}
    getMaxTemp(){}
    getMinTemp(){}
    getForecast(){}
  }
</script>
