<script setup>
import { ref } from 'vue'

const users = ["Pepe", "Ana", "Juana", "Lola"]

const isChecked = ref ('true')
</script>
<template>
    <ul>
        <li v-for="(user, index) in users" :key="index">{{ index }} {{ user }}</li>
    </ul>

    <!-- <input value="message" placeholder="edit me" class="border border-red-950"/> -->
    <input type="checkbox" id="check" v-model="isChecked"/>
    <label for="check">Pichame</label>

    <div class="bg-blue-400 text-white rounded py-1 px-2"
        :class="{'bg-orange-500': isChecked}">
        Este es un mensaje
    </div>

    <div v-show="isChecked">
        Este es un mensaje que podria ocultar
    </div>

    <div v-if="isChecked">
        Este es un mensaje que podria ocultar
    </div>

    <div v-else="isChecked">
        Mensaje
    </div>

</template>