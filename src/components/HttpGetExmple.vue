<script setup>
    import { ref } from 'vue';
    import axios from 'axios';

    const items = ref([]);

    axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(response => {
            items.value = response.data;
        });
        
</script>

<template>
    <h1>Http Get Example</h1>
    <ul>
        <li v-for="item in items" :key="item.id">{{ item.title }}</li>
    </ul>
</template>


