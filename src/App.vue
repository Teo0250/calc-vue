<script setup>
import { watch, ref } from 'vue';

  const number1 = ref(0);
  const operador = ref('+');
  const number2 = ref(0);
  const resultado = ref(0);

  watch([number1, operador, number2], () => {
    switch (operador.value) {
      case '+':
        resultado.value = number1.value + number2.value;
        break;
      case '-':
        resultado.value = number1.value - number2.value;
        break;
      case '*':
        resultado.value = number1.value * number2.value;
        break;
      case '/':
        resultado.value = number1.value / number2.value;
        break;
    }
  });
</script>
<template>
    <div class="container">
    <header class="p-5 mb-4 mt-4 text-center bg-light rounded-3">
      <h1>Calculadora aritmética</h1>
    </header>
    <form class="form-control">
      <div class="row">
        <div class="col">
          <input class="form-control text-center" type="number" v-model="number1" placeholder="Digite um número" />
        </div>
        <div class="col-1">
          <select class="form-control text-center" v-model="operador">
            <option class="text-center" value="+">+</option>
            <option class="text-center" value="-">-</option>
            <option class="text-center" value="*">*</option>
            <option class="text-center" value="/">/</option>
          </select>
        </div>
        <div class="col">
          <input class="form-control text-center" type="number" v-model="number2" placeholder="Digite outro número" />
        </div>
      </div>
      <div class="row-5">
        <div class="col">
          <h2 class="mt-5 text-center">
            Resultado: {{ resultado }}
          </h2>
        </div>
      </div>
    </form>
  </div>
</template>