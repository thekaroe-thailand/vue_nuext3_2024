<script setup>
    import { ref } from 'vue';

    const todoList = ref([
        { id: 1, title: 'Learn Vue 3', completed: false },
        { id: 2, title: 'Build a todo app', completed: false },
        { id: 3, title: 'Deploy to production', completed: false },
    ]);

    const addTodo = () => {
        const title  = 'new todo is ' + todoList.value.length + 1;
        const newTodo = { id: todoList.value.length + 1, title: title, completed: false };
        todoList.value.push(newTodo);
    }

    const removeTodo = (id) => {
        // 1,2,3,4,5
        // id = 3
        // 1,2,4,5
        todoList.value = todoList.value.filter(todo => todo.id !== id);
    }
</script>

<template>
    <ul>
        <li v-for="todo in todoList" :key="todo.id">
            {{  todo.title }}
            <button @click="removeTodo(todo.id)">Remove</button>
        </li>
    </ul>
    <button @click="addTodo">Add Todo</button>
</template>