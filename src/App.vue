<script setup>
import { ref, computed } from 'vue';

const numero1 = ref(0);
const numero2 = ref(0);
const operacao = ref('soma');

const resultado = computed(() => {
  switch (operacao.value) {
    case 'soma':
      return numero1.value + numero2.value;
    case 'subtracao':
      return numero1.value - numero2.value;
    case 'multiplicacao':
      return numero1.value * numero2.value;
    case 'divisao':
      return numero2.value !== 0 ? numero1.value / numero2.value : 'Erro: divisão por zero';
    default:
      return 0;
  }
});
</script>

<template>
  <div class="container">
    <h1>Calculadora Aritmética</h1>
    
    <div>
      <label for="numero1">Número 1:</label>
      <input type="number" v-model="numero1" id="numero1" />
    </div>
    
    <div>
      <label for="numero2">Número 2:</label>
      <input type="number" v-model="numero2" id="numero2" />
    </div>

    <div>
      <label for="operacao">Operação:</label>
      <select v-model="operacao" id="operacao">
        <option value="soma">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="divisao">/</option>
      </select>
    </div>

    <h2>Resultado: {{ resultado }}</h2>
  </div>
</template>

<style scoped>
.container {
  max-width: 400px;
  margin: 0 auto;
  text-align: center;
  padding: 20px;
}
input, select {
  margin-bottom: 10px;
}
</style>
