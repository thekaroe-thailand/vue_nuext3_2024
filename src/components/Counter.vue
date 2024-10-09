<script setup>
  import { ref } from 'vue'

  const count = ref(0)
</script>

<template>
  <button @click="count++">Upper</button>
  <button @click="count--">Lower</button>

  <div>Counter: {{ count }}</div>
</template>

