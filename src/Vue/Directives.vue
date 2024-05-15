<script setup>
import {ref} from "vue"

let msg = ref("soy un mensaje")
let checked = ref(false)
let data =["hola","mundo","adios"]

//let filtered = data.filter((word) => word.includes("o")) 

let filtered = data.filter(function(word){
    return word.includes("0")
})
</script>
<template>
    <input class="border border-red-500" :class="{' border-green-500':checked}" v-model="msg"/>
     
    <div :title="msg">
        {{msg}}
    </div>
    
    <label for="check">Selecione {{ checked }}</label>
    <input type="checkbox" v-model="checked">

    <ul>
        <li v-for="(text , index) in filtered" :key="index">
            {{ text }}
        </li>
    </ul>
</template>