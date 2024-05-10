<script setup>
import { ref } from 'vue'

const todos = ref(['Estudiar bastante'])
const todo = ref('')

function add() {
    console.log(todo.value)
    todos.value.unshift(todo.value)
    todo.value = ''
}

</script>

<template>
    <div class="rounded shadow bg-slate-200 max-w-96 mx-auto mt-10 py-6 px-5">
        <div>
            <input v-model="todo" class="w-4/5 outline-none rounded px-2 mb-2"/>
            <button @click="add" class="w-1/5 bg-green-500 text-white text-center hover:bg-green-300">
                +
            </button>
        </div>
        <div class="mt-3">
            <div v-for="(todo, i) in todos" :key="i" class="bg-orange-300 rounded px-1 mb-2">{{ todo }}</div>
        </div>
    </div>
</template>
