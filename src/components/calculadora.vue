<template>
    <div class="calculator">
      <label for="numero1">Número 1:</label>
      <input v-model="numero1" type="number" id="numero1" @input="calcularResultado" />
  
      <label for="operacao">Operação:</label>
      <select v-model="operacao" id="operacao" @change="calcularResultado">
        <option value="soma">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="divisao">/</option>
      </select>
  
      <label for="numero2">Número 2:</label>
      <input v-model="numero2" type="number" id="numero2" @input="calcularResultado" />
  
      <div class="resultado">
        <strong>Resultado:</strong> {{ resultado }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        numero1: 0,
        operacao: 'soma',
        numero2: 0,
        resultado: 0,
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
      },
    },
  };
  </script>
  
  <style scoped>
  .calculator {
    max-width: 400px;
    margin: 20px auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  
  label {
    display: block;
    margin-bottom: 5px;
  }
  
  input,
  select {
    width: 100%;
    padding: 8px;
    margin-bottom: 15px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }
  
  .resultado {
    margin-top: 15px;
    font-size: 18px;
  }
  </style>
  