<template>
  <div id="app">
      <h1 class="title">Conversor de Moedas</h1>
      <div class="line">
          <Converter moeda-a="USD" moeda-b="BRL" />
          <Converter moeda-a="BRL" moeda-b="USD" />
      </div>
      <div class="line">
          <Converter moeda-a="CAD" moeda-b="BRL" />
          <Converter moeda-a="BRL" moeda-b="CAD" />
      </div>
      <div class="line">
          <Converter moeda-a="EUR" moeda-b="BRL" />
          <Converter moeda-a="BRL" moeda-b="EUR" />
      </div>

  </div>
</template>

<script>

import Converter from './components/Converter';
export default {
  name: 'app',
  components: {Converter}
}
</script>

<style>
body {
    margin: 0;
}

#app {
  max-width: 900px;
  margin: auto;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.line {
    margin-top: 15px;
    display: flex;
    justify-content: space-around;
}

.title {
    text-align: center;
}
</style>
