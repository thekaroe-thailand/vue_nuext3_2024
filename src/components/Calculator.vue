<script setup>
  import { ref } from 'vue'

  const num1 = ref(0)
  const num2 = ref(0)
  const result = ref(0)

  const add = () => {
    result.value = num1.value + num2.value
  }

  const subtract = () => {
    result.value = num1.value - num2.value
  }

  const multiply = () => {
    result.value = num1.value * num2.value
  }

  const divide = () => {
    result.value = num1.value / num2.value
  }
</script>

<template>
  <div>
    <input type="number" v-model="num1" />
    <input type="number" v-model="num2" />
    <button @click="add">Add</button>
    <button @click="subtract">Subtract</button>
    <button @click="multiply">Multiply</button>
    <button @click="divide">Divide</button>
    <div>Result: {{ result }}</div>
  </div>
</template>

