<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    
    <div class="calculator">
      <input type="number" v-model="num1" placeholder="Número 1">
      <select v-model="operation">
        <option value="add">Somar</option>
        <option value="subtract">Subtrair</option>
        <option value="multiply">Multiplicar</option>
        <option value="divide">Dividir</option>
      </select>
      <input type="number" v-model="num2" placeholder="Número 2">
    </div>

    <div class="result">
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'add',
    };
  },
  computed: {
    result() {
      const n1 = parseFloat(this.num1);
      const n2 = parseFloat(this.num2);

      switch (this.operation) {
        case 'add':
          return n1 + n2;
        case 'subtract':
          return n1 - n2;
        case 'multiply':
          return n1 * n2;
        case 'divide':
          return n2 !== 0 ? n1 / n2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    },
  },
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 50px;
}

.calculator {
  margin: 20px 0;
}

input, select {
  margin: 10px;
  padding: 5px;
  font-size: 16px;
}

.result h2 {
  margin-top: 20px;
  color: #333;
}
</style>
