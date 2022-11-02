<template>
  <div id="app">
    <main>
      <img class="logo" src="./assets/logo.png" alt="Vue Weather">
      <h3>BUSCAR CIDADE</h3>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="Pesquisar...">
      </div>

      <div class="weather-container">
        <div class="weather-display">
          <div class="location-bx">
            <div class="location">João Pessoa, PB</div>
            <div class="date">Segunda-feira, 31 de outubro de 2022</div>
          </div>

          <div class="weather-bx">
            <div class="temperature">25º</div>
            <div class="weather">Chuva</div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
  export default {
    name: 'App'
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