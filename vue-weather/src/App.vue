<template>
  <div id="app">
    <main>
      <h3>BUSCAR CIDADE</h3>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="Pesquisar...">
      </div>

      <div class="weather-container">
        <div class="location-bx">
          <div class="location">João Pessoa, PB</div>
          <div class="date">Segunda-feira, 31 de outubro de 2022</div>
        </div>

        <div class="weather-bx">
          <div class="temperature">25º</div>
          <div class="weather">Chuva</div>
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
}
main {
  min-height: 100vh;
  padding: 25px;
  background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.25), rgba(0, 0, 0, 0.75));
}
.search-box {
  width: 100%;
  margin: 15px 0 30px  0;
}
.search-box .search-bar {
  display: relative;
  text-align: center;
  width: 25%;
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
</style>