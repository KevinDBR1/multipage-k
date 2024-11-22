<script setup>
import { ref } from "vue";
const name = "Kevin"
let counter = ref(5)
let characters = ref([])

function add() {
    counter.value++
    console.log(counter);
    characters.value.push(counter.value)

}
function erase() {
    counter.value--
    console.log(counter);

}

</script>

<template>
    <div class="mx-auto max-w-96 rounded py-4 px-6 bg-blue-300">
        hola mundo {{ name }}

        <div 
            v-if="counter > 0"
            class="flex items-center justify-center rounded-full size-9 bg-blue-600 text-white">
            {{ counter }}
        </div>
        <div v-else>
            nadie ha escrito :(
        </div>

            <div 
                @click="add()" class="flex items-center justify-center rounded-full size-5 bg-red-600 text-white"
                >
                +
            </div>
            <div 
                @click="erase()" class="flex items-center justify-center rounded-full size-5 bg-red-600 text-white"
                >
                -
            </div>
        <div v-for="(name,index) in characters" :key="index" class="flex bg-green-500 mb-1">
            {{ name }}
        </div>
    </div>
</template>