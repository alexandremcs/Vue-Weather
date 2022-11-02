<template>
  <div id="app">
    <main>
      <img class="logo" src="./assets/logo.png" alt="Vue Weather">
      <h3>BUSCAR CIDADE</h3>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="Pesquisar..." v-model="query" @keypress="fetchWeather">
      </div>

      <div class="weather-container" v-if="typeof weather.main != 'undefined'" >
        <div class="weather-display">
          <div class="location-bx">
            <div class="location">{{ weather.name }}, {{ weather.sys.country }}</div>
            <div class="date">{{ dateBuilder() }}</div>
          </div>

          <div class="weather-bx">
            <div class="temperature">{{ Math.round(weather.main.temp) }}°<small>c</small></div>
            <div class="weather">{{ weather.weather[0].main }}</div>
            <img :src='weatherIcon()' />
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data () {
      return {
        api_key: '36819ca66f3207df4e42e3325a296b7a',
        url_base: 'https://api.openweathermap.org/data/2.5/',
        query: '',
        weather: {}
      }
    },
    methods: {
      fetchWeather (e) {
        if (e.key == "Enter") {
          fetch(`${this.url_base}weather?q=${this.query}&units=metric&APPID=${this.api_key}`).then(
            res => {
              return res.json();
            }).then(this.setResults);
        }
      },
      setResults (results) {
        this.weather = results;
      },
      weatherIcon () {
        return `http://openweathermap.org/img/wn/${this.weather.weather[0].icon}@2x.png`
      },
      dateBuilder () {
        let d = new Date();
        let months = ["Janeiro", "Fevereiro", "Março", "Abril", "Maio", "Junho", "Julho", "Agosto", "Setembro", "Outubro", "Novembro", "Dezembro"];
        let days = ["Domingo", "Segunda-feira", "Terça-feira", "Quarta-feira", "Quinta-feira", "Sexta-feira", "Sábado"];
        let day = days[d.getDay()];
        let date = d.getDate();
        let month = months[d.getMonth()];
        let year = d.getFullYear();
        return `${day}, ${date} de ${month} de ${year}`;
      }
    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;0,700;1,400&display=swap');

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  body {
    font-family: 'montserrat', sans-serif;
    text-align: center;
    background-image: url(./assets/bg.jpg);
  }
  .logo {
    height: 200px;
    margin: 15px 0 30px  0;
  }
  h3 {
    color: white;
  }
  main {
    min-height: 100vh;
    padding: 25px;
    background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 1));
  }
  .search-box {
    width: 100%;
    margin: 15px 0 30px  0;
  }
  .search-box .search-bar {
    text-align: center;
    width: 20%;
    padding: 15px;  
    color: #313131;
    font-size: 18px;
    appearance: none;
    border:none;
    outline: none;
    background: none;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
    background-color: rgba(255, 255, 255, 0.5);
    border-radius: 16px;
    transition: 0.4s;
  }
  .search-box .search-bar:focus {
    box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
    background-color: rgba(255, 255, 255, 0.75);
  }
  .weather-container {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
  .weather-display {
    width: auto;
    padding: 25px;
    border-radius: 20px;
    box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
    background-color: #0f77ff;
  }
  .location-bx .location {
    color: #FFF;
    font-size: 30px;
    font-weight: 500;
    text-align: center;
    text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
  }
  .location-bx .date {
    color: #FFF;
    font-size: 18x;
    font-weight: 300;
    font-style: italic;
    text-align: center;
  }
  .weather-bx {
    text-align: center;
  }
  .weather-bx .temperature {
    display: inline-block;
    padding: 15px 25px;
    color: #FFF;
    font-size: 80px;
    font-weight: bold;
    text-shadow: 3px 4px rgba(0, 0, 0, 0.25);
    background-color:rgba(255, 255, 255, 0.3);
    border-radius: 16px;
    margin: 30px 0px;
    box-shadow: 3px 4px rgba(0, 0, 0, 0.25);
  }
  .weather-bx .weather {
    color: #FFF;
    font-size: 38px;
    font-weight: 700;
    font-style: italic;
    text-shadow: 3px 4px rgba(0, 0, 0, 0.25);
  }
</style>