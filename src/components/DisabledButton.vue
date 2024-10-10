<script setup>
    import { ref } from 'vue'

    const isDisabled = ref(false);
</script>

<template>
    <input type="checkbox" v-model="isDisabled" /> Disable button
    <button :disabled="isDisabled">Click me</button>
    <p>Is disabled: {{ isDisabled }}</p>
</template>
