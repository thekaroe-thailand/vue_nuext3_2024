<script setup>
    import { ref } from 'vue';

    const isVisible = ref(true);
</script>

<template>
    <h1 v-if="isVisible">Hello World</h1>
</template>