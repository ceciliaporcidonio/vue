<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div class="calculator">
      <input type="number" v-model.number="number1" placeholder="Número 1" />
      <input type="number" v-model.number="number2" placeholder="Número 2" />
      <select v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
      <p>Resultado: {{ result }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add'
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.number1 + this.number2;
        case 'subtract':
          return this.number1 - this.number2;
        case 'multiply':
          return this.number1 * this.number2;
        case 'divide':
          return this.number2 !== 0 ? this.number1 / this.number2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    }
  }
};
</script>

<style scoped>
#app {
  text-align: center;
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  padding: 20px;
}

.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  background-color: #fff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

input, select {
  padding: 10px;
  font-size: 1em;
  border: 1px solid #ccc;
  border-radius: 5px;
  width: 200px;
  box-sizing: border-box;
}

select {
  cursor: pointer;
}

p {
  font-size: 1.5em;
  font-weight: bold;
  color: #333;
}

input:focus, select:focus {
  outline: none;
  border-color: #007bff;
  box-shadow: 0 0 5px rgba(0, 123, 255, 0.5);
}
</style>
