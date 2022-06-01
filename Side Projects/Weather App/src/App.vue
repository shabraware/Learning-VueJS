<template>
  <main>
    <div class="search-box">
      <input
        type="text"
        class="search-bar"
        placeholder="Search..."
        v-model="query"
        @keypress.enter="fetchDate"
      />
    </div>
    <div class="weather-wrap" v-if="weather.name">
      <div class="location-box">
        <div class="location">
          {{ weather.name }}, {{ weather.sys.country }}
        </div>
        <div class="date">{{ dateBuilder() }}</div>
      </div>
      <div class="weather-box">
        <div class="temp">{{ Math.round(weather.main.temp) }}°c</div>
        <div class="weather">{{ weather.weather[0].main }}</div>
      </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios';
export default {
  name: 'App',
  data: function () {
    return {
      // API key & Base URL are stored here for simplicity
      apiKey: '',
      baseUrl: 'https://api.openweathermap.org/data/2.5/',
      query: '',
      weather: {},
    };
  },
  methods: {
    fetchDate: async function () {
      try {
        const response = await axios(
          `${this.baseUrl}weather?q=${this.query}&units=metric&APPID=${this.apiKey}`
        );
        this.weather = response.data;
        console.log(response.data);
      } catch (error) {
        console.log(error);
      }
    },
    dateBuilder() {
      let months = [
        'January',
        'February',
        'March',
        'April',
        'May',
        'June',
        'July',
        'August',
        'September',
        'October',
        'November',
        'December',
      ];
      let days = [
        'Sunday',
        'Monday',
        'Tuesday',
        'Wednesday',
        'Thursday',
        'Friday',
        'Saturday',
      ];
      let d = new Date();
      let day = days[d.getDay()];
      let month = months[d.getMonth()];
      let year = d.getFullYear();
      let date = d.getDate();
      return `${day} ${date} ${month} ${year}`;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: 'montserrat', sans-serif;
}
main {
  height: 100vh;
  padding: 25px;
  background-image: linear-gradient(
      to bottom,
      rgba(0, 0, 0, 0.25),
      rgba(0, 0, 0, 0.75)
    ),
    url('./assets/cold-bg.jpg');
  background-size: cover;
  background-position: bottom;
  /* transition: 0.4s; */
}
.search-box {
  margin-bottom: 30px;
}
.search-box .search-bar {
  display: block;
  padding: 15px;
  width: 100%;
  color: #313131;
  font-size: 20px;
  border: none;
  outline: none;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 0 16px 0 16px;
  transition: 0.4s;
}
.search-box .search-bar:hover,
.search-box .search-bar:focus {
  box-shadow: 0 0 16px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.75);
  border-radius: 16px 0 16px 0;
}

.location-box {
  color: #fff;
  text-align: center;
}
.location-box .location {
  font-size: 32px;
  font-weight: 500;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
}
.location-box .date {
  font-size: 20px;
  font-weight: 300;
  font-style: italic;
}

.weather-box {
  text-align: center;
  color: #fff;
}

.weather-box .temp {
  display: inline-block;
  margin: 30px 0px;
  border-radius: 16px;
  padding: 10px 25px;
  font-size: 102px;
  font-weight: 900;
  background-color: rgba(255, 255, 255, 0.25);
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}

.weather-box .weather {
  font-size: 48px;
  font-weight: 700;
  font-style: italic;
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
</style>
