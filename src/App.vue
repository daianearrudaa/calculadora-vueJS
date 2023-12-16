<script setup>

import { reactive } from 'vue';



const estado = reactive({
  num1: '',
  num2: '',
})

let operacao = " ";

const resultado = () => {
  const num1 = parseFloat(estado.num1);
  const num2 = parseFloat(estado.num2);



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

}


</script>

<template>
  <div class="container d-flex mt-5 flex-column w-100 bg-light">
    <h1 class="text-center mt-5">Calculadora</h1>
    <input v-model="estado.num1" class="w-25 text-center mt-5 mx-auto" type="number" placeholder="Digite um número">
    <label class="w-10 text-center mt-5 mx-auto">
      Selecione uma operação
      <select v-model="operacao" class="w-100">
        <option value="soma">Soma +</option>
        <option value="multiplicacao">Multiplicação x</option>
        <option value="divisao">Divisão /</option>
      </select>
    </label>
    <input v-model="estado.num2" class="w-25 text-center mt-5 mx-auto" type="number" placeholder="Digite um número">

    <div class="p-2 mt-5 mb-5 mx-auto rounded-4 bg-info text-white">
      <div>A resposta é :</div>
      <div class="text-center fs-2">{{ resultado() }}</div>
    </div>
  </div>
</template>

<style scoped></style>
