
<script setup>
import { defineProps } from 'vue';

const props = defineProps(['numero1', 'numero2', 'resultadoFinal', 'operacaoEscolhida', 'calcular']);
</script>

<template>
  <h1 class="text-center mt-5" >Calculadora</h1>
  <input v-model="props.numero1" class="w-25 text-center mt-5 mx-auto" type="number" placeholder="Digite um número">
  <select v-model="props.operacaoEscolhida" class="w-10 text-center mt-5 mx-auto">
    <option  value="soma">Soma +</option>
    <option value="multiplicacao">Multiplicação x</option>
    <option value="divisao">Divisão /</option>
  </select>
  <input v-model="props.numero2"  class="w-25 text-center mt-5 mx-auto" type="number" placeholder="Digite um número">
  
  <div class="p-2 mt-5 mb-5 mx-auto rounded-4 bg-info text-white"> 
    <div>A resposta é :</div>
    <div class="text-center fs-2">{{ props.resultadoFinal }}</div>
  </div>
  </template>