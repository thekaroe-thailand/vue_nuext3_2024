<script setup>
    import axios from 'axios';
    import { ref } from 'vue';

    const title = ref('');
    const body = ref('');
    const userId = ref(1);

    const handleSubmit = () => {
        const payload = {
            title: title.value,
            body: body.value,
            userId: userId.value
        };
        axios.put(`https://jsonplaceholder.typicode.com/posts/1`, payload)
            .then(response => {
                console.log('Post updated:', response.data);
            })
    };
</script>

<template>
    <h1>Http Put Example</h1>
    <form @submit.prevent="handleSubmit">
        <input type="text" v-model="title" placeholder="Title" required />
        <input type="text" v-model="body" placeholder="Body" required />
        <button type="submit">Update Post</button>
    </form>
</template>
