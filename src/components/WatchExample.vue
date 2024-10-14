<script setup>
    import { ref, watch } from 'vue';

    const price = ref(100);
    const quantity = ref(2);
    const total = ref(0);

    watch([price, quantity], ([newPrice, newQuantity]) => {
        total.value = newPrice * newQuantity;
    });
</script>

<template>
    <p>Price: {{ price }}</p>
    <input type="number" v-model="price" />

    <p>Quantity: {{ quantity }}</p>
    <input type="number" v-model="quantity" />
    
    <p>Total: {{ total }}</p>
</template>