<script setup>
    import { ref } from 'vue'

    const textbox = ref(null); // ใช้ ref กับ element ที่ต้องการจะจับคู่ HTMLElement

    const focusTextbox = () => {
        textbox.value.focus(); // เรียกใช้ focus() เมื่อฟังก์ชันถูกเรียกใช้
    }
</script>

<template>
    <input type="text" ref="textbox" />
    <button @click="focusTextbox">Focus Textbox</button>
</template>