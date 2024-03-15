<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <input type="number" v-model.number="numero1" @input="calcularResultado">
    <select v-model="operacao" @change="calcularResultado">
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>
    <input type="number" v-model.number="numero2" @input="calcularResultado">
    <div>
      Resultado: {{ resultado }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma',
      resultado: 0
    };
  },
  methods: {
    calcularResultado() {
      switch (this.operacao) {
        case 'soma':
          this.resultado = this.numero1 + this.numero2;
          break;
        case 'subtracao':
          this.resultado = this.numero1 - this.numero2;
          break;
        case 'multiplicacao':
          this.resultado = this.numero1 * this.numero2;
          break;
        case 'divisao':
          this.resultado = this.numero1 / this.numero2;
          break;
        default:
          this.resultado = 0;
      }
    }
  }
};
</script>

<style>
#app {
  font-family: Roboto, sans-serif;
  font-weight: bold;
  text-align: center;
  margin-top: 50px;
}

select, input{
  margin: 10px;
  padding: 5px;
}
</style>
