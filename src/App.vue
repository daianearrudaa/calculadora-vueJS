<script setup>
import { reactive } from 'vue';


const estado = reactive({
  num1: 0,
  num2: 0,
  operacao: 'soma',
});


const resultado = () => {
  const { num1, num2, operacao } = estado;


  switch (operacao) {
    case 'soma':
      return num1 + num2;
    case 'multiplicacao':
      return num1 * num2;
    case 'divisao':
      return num1 / num2;
    default:
      return 0;
  }
};
</script>


<template>
  <body>
  <div class="container d-flex mt-5 flex-column w-100">
    <h1 class="text-center mt-5">Calculadora</h1>
    <input v-model="estado.num1" class="text-center mt-5 mx-auto rounded-4" type="number" placeholder="Digite um número">
    <label class="w-10 text-center mt-5 mx-auto">
      <div><strong>Selecione uma operação</strong></div>
      <select v-model="estado.operacao" class="w-90 rounded-4 text-center border-3">
        <option value="soma">Soma +</option>
        <option value="multiplicacao">Multiplicação x</option>
        <option value="divisao">Divisão /</option>
      </select>
    </label>
    <input v-model="estado.num2" class="text-center mt-5 mx-auto rounded-4" type="number" placeholder="Digite um número">


    <div class="p-2 mt-5 mb-5 mx-auto rounded-4 bg-info text-white">
      <div>A resposta é :</div>
      <div class="text-center fs-2">{{ resultado() }}</div>
    </div>
  </div>
</body>
</template>


<style scoped>
body {
  display: flex;
  width: 100%;
  height: 100vh;
  background-image: url('./assets/image/imagem-fundo.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
}
</style>