<script setup>
    import { ref } from 'vue'

    const childMessage = ref('Hello from parent')

    const handleClick = () => {
        childMessage.value = 'Hello from child'
    }

    const emit = defineEmits(['myEvent']);

    const handleClickFromParent = () => {
        emit('myEvent', 'Hello from child') // eventName, message
    }
</script>

<template>
    <h2>Parent Component</h2>
    <h1>{{ childMessage }}</h1>
    <button @click="handleClick">Click me</button>
    <button @click="handleClickFromParent">Click me from parent</button>
    <slot name="myHeader">Default Header</slot>
</template>