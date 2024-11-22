<script setup>
import { ref } from "vue";
console.log("Yender esta de negro");
const name = "andres";

let characters= ref([])

var cantidad = ref(5);
function anadir() {
    cantidad.value++;
    characters.value.push(cantidad.value)
}
function restar() {
    cantidad.value--;
    characters.value.pop();
}
</script>

<template>
    <div class="mx-auto max-w-96 rounded py-4 px-6 bg-blue-200 select-none flex flex-col justify-center items-center">
        Hola {{ name }}
        <div class="flex justify-center items-center size-10 bg-green-300 rounded-full" v-if="cantidad>0">
            {{ cantidad }}
        </div>
        <div v-else>
            Nadie te escribe
        </div>
        <div class="flex">
            <div @click="anadir()"
                class="flex justify-center items-center size-10 bg-green-300 rounded-full cursor-pointer">
                +
            </div>
            <div @click="restar()"
                class="flex justify-center items-center size-10 bg-green-300 rounded-full cursor-pointer">
                -
            </div>
        </div>
    </div>
    <div class="bg-green-300 mb-1" v-for="(name, index) in characters":key="index">
{{ name }}
    </div>
</template>
