<!-- EJERCICIO1: Crear 2 inputs para numeros, con una seccion de radio buttoms para elegir el procedimiento entre suma, resta, multiplicaion y division, crear ademas validacion en division, no es posible dividir entre 0  -->

<template>

<div>
  <h1>Calculadora</h1>
  <input type="number" v-model="num1" />
  <input type="number" v-model="num2" />
  <div>
    <input type="radio" v-model="operacion" value="suma" /> Suma
    <input type="radio" v-model="operacion" value="resta" /> Resta
    <input type="radio" v-model="operacion" value="multiplicacion" /> Multiplicacion
    <input type="radio" v-model="operacion" value="division" /> Division
  </div>
  <button @click="calcular">Calcular</button>
  <p>Resultado: {{ resultado }}</p>

</div>

</template>



<style scoped>

</style>



<script setup>
import { ref } from 'vue'

const num1 = ref(0)
const num2 = ref(0)
const operacion = ref('')
const resultado = ref(0)

const calcular = () => {
  switch (operacion.value) {
    case 'suma':
      resultado.value = num1.value + num2.value
      break
    case 'resta':
      resultado.value = num1.value - num2.value
      break
    case 'multiplicacion':
      resultado.value = num1.value * num2.value
      break
    case 'division':
      if (num2.value === 0) {
        resultado.value = 'No se puede dividir entre 0'
      } else {
        resultado.value = num1.value / num2.value
      }
      break
  }
}

</script>