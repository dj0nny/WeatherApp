<template>
  <div class="city-card weather-card">
    <h1>{{city.name}}</h1>
    <img :src="'https://s3-us-west-2.amazonaws.com/s.cdpn.io/162656/' + city.weather[0].icon + '.svg'" />
    <div class="weather-data">
      <div class="weather-desc">
        {{city.weather[0].main}} <br>
        {{city.weather[0].description}}
      </div>
      <div class="temperature">
        <span class="entry">Temperature: </span> {{city.main.temp}} °C <br>
        <span class="entry">Min temperature: </span> {{city.main.temp_min}} °C <br>
        <span class="entry">Max temperature: </span> {{city.main.temp_max}} °C <br>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityCard',
  props: {
    city: Object,
  },
};
</script>
