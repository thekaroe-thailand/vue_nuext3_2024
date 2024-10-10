<script setup>
    import { ref } from 'vue'

    const isChecked = ref(false)
    const selectedOption = ref('')

    // options key and value
    const options = ref([
        { key: '100', value: 'Option 1' },
        { key: '200', value: 'Option 2' },
        { key: '300', value: 'Option 3' },
    ]);
</script>

<template>
    <input type="checkbox" v-model="isChecked" /> Agree to terms and conditions
    <p>Is checked: {{ isChecked }}</p>
    <span v-for="option in options" :key="option.key">
        <input type="radio" v-model="selectedOption" :value="option.key" /> {{ option.value }}
    </span>
    <p>Selected option: {{ selectedOption }}</p>
</template>