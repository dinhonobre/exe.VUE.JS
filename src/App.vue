<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div>
      <input type="number" v-model.number="numero1" placeholder="Número 1" />
      <select v-model="operacao">
        <option value="+">Somar</option>
        <option value="-">Subtrair</option>
        <option value="*">Multiplicar</option>
        <option value="/">Dividir</option>
      </select>
      <input type="number" v-model.number="numero2" placeholder="Número 2" />
    </div>
    <div>
      <h2>Resultado: {{ resultado }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: "+",
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case "+":
          return this.numero1 + this.numero2;
        case "-":
          return this.numero1 - this.numero2;
        case "*":
          return this.numero1 * this.numero2;
        case "/":
          return this.numero2 !== 0 ? this.numero1 / this.numero2 : "Erro: Divisão por zero";
        default:
          return "Operação inválida";
      }
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
  margin: 50px;
}
input, select {
  margin: 10px;
  padding: 10px;
  font-size: 1em;
}
h2 {
  color: #2c3e50;
}
</style>
