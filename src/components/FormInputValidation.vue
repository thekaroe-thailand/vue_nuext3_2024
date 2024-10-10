<script setup>
    import { ref } from 'vue'

    const name = ref('')
    const nameError = ref('')

    const handleSubmit = () => {
        if (name.value.length < 3) {
            nameError.value = 'Name must be at least 3 characters'
        } else {
            nameError.value = ''
        }
    }
</script>

<template>
    <form @submit.prevent="handleSubmit">
        <input type="text" v-model="name" placeholder="Enter your name" />
        <p>{{ nameError }}</p>
        <button type="submit">Submit</button>
    </form>
</template>