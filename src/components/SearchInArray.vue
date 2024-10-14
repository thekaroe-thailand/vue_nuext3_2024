<script setup>
    import { ref, computed } from 'vue';

    const items = ref([
        { id: 1, name: 'Item 1' },
        { id: 2, name: 'Item 2' },
        { id: 3, name: 'Item 3' },
    ]); 

    const search = ref('');

    const filteredItems = computed(() => {
        return items.value.filter(item => item.name.includes(search.value));
    });
</script>

<template>
    <h1>Search in Array</h1>
    <input type="text" v-model="search" placeholder="Search..." />
    <ul>
        <li v-for="item in filteredItems" :key="item.id">{{ item.name }}</li>
    </ul>
</template>