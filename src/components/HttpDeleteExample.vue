<script setup>
    import axios from 'axios';

    const handleDelete = () => {
        axios.delete(`https://jsonplaceholder.typicode.com/posts/1`)
            .then(response => {
                console.log('Post deleted:', response.data);
            })
            .catch(error => {
                console.error('Error deleting post:', error);
            });
    };
</script>

<template>
    <h1>Http Delete Example</h1>
    <button @click="handleDelete">Delete Post</button>
</template>
