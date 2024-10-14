<script setup>
    import { ref, watch } from 'vue';

    const items = ref([
        { id: 1, name: 'Item 1' },
        { id: 2, name: 'Item 2' },
        { id: 3, name: 'Item 3' },
    ]);
    
    // ข้อมูลที่จะใช้ค้นหา
    const search = ref('');
    const filteredItems = ref([...items.value]);

    // watch การเปลี่ยนแปลงของ search และกรองข้อมูลใหม่ทุกครั้งที่ search มีการเปลี่ยนแปลง
    watch(search, (newValue) => {
        filteredItems.value = items.value.filter(
            item => item.name.includes(newValue)
        );
    });
</script>

<template>
    <h1>Seach in Array (No Computed)</h1>
    <input type="text" v-model="search" placeholder="Search..." />
    <ul>
        <li v-for="item in filteredItems" :key="item.id">{{ item.name }}</li>
    </ul>
</template>