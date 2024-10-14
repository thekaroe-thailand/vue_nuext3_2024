<script setup>
    import { ref, computed } from 'vue';

    const price = ref(100);
    const quantity = ref(2);

    const total = computed(() => {
        return price.value * quantity.value;
    });
</script>

<template>
    <p>Price: {{ price }}</p>
    <input type="number" v-model="price" />

    <p>Quantity: {{ quantity }}</p>
    <input type="number" v-model="quantity" />
    
    <p>Total: {{ total }}</p>
</template>