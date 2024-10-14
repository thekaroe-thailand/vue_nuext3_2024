<script setup>  
    import axios from 'axios';
    import { ref } from 'vue';

    const title = ref('');
    const body = ref('');
    const userId = ref(1);

    const handleSubmit = () => {
        axios.post('https://jsonplaceholder.typicode.com/posts', {
            title: title.value,
            body: body.value,
            userId: userId.value
        })
        .then(response => {
            console.log('Post created:', response.data);
        })
    };
</script>

<template>
    <h1>Http Post Example</h1>
    <form @submit.prevent="handleSubmit">
        <input type="text" v-model="title" placeholder="Title" required />
        <input type="text" v-model="body" placeholder="Body" required />
        <button type="submit">Create Post</button>
    </form>
</template>
