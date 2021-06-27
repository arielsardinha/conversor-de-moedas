<template>
  <div id="app" class="app">
    <div>
      <Conversor moeda-a="USD" moeda-b="BRL" />
      <Conversor moeda-a="CAD" moeda-b="BRL" />
      <Conversor moeda-a="EUR" moeda-b="BRL" />
    </div>
    <div>
      <Conversor moeda-a="BRL" moeda-b="USD" />
      <Conversor moeda-a="BRL" moeda-b="CAD" />
      <Conversor moeda-a="BRL" moeda-b="EUR" />
    </div>
  </div>
</template>

<script>
import Conversor from "./components/Conversor.vue";

export default {
  name: "App",
  components: {
    Conversor,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.app {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
  div {
    margin: 30px 0;
  }
}
</style>
