<script setup>
  const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]
</script>

<template>
  <table>
    <tr v-for="number in numbers" :key="number">
      <td>2 x {{ number }} = {{ 2 * number }}</td>
    </tr>
  </table>
</template>