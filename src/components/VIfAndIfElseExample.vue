<script setup>
    import { ref } from 'vue';

    const isVisible = ref(true);
</script>

<template>
    <h1 v-if="isVisible">Hello if</h1>
    <h1 v-else>Hello else</h1>
    <button @click="isVisible = !isVisible">Toggle Visibility</button>
</template>