<template>
  <div>
    <h2>{{ moedaA }} para {{ moedaB }}</h2>
    <input type="number" v-model="moedaA_value" v-bind:placeholder="moedaA" />
    <input v-on:click="converter" type="button" value="Converter" />
    <h2>{{ moedaB_value }}</h2>
  </div>
</template>
<script>
export default {
  name: "Conversor",
  props: ["moedaA", "moedaB"],
  data() {
    return {
      moedaA_value: "",
      moedaB_value: 0,
    };
  },
  methods: {
    converter() {
      let de_para = `${this.moedaA}_${this.moedaB}`;
      let url = `https://free.currconv.com/api/v7/convert?q=${de_para}&compact=ultra&apiKey=856893ec6a4b041bbd7e`;
      fetch(url)
        .then((res) => {
          return res.json();
        })
        .then((resConvertida) => {
          let cotacao = resConvertida[de_para];
          this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(
            2
          );
        });
    },
  },
};
</script>
<style scoped lang="scss">
div {
  border: solid 1px black;
  width: 300px;
  border-radius: 5px;
  input[type="number"] {
    padding: 1px 5px;
  }
}
</style>
