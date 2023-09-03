<script setup>
import {ref} from 'vue'

const sheep = ref(true)
const happy = ref(true)
const seek = ref(true)
const pets = ref(true)
const checked = ref(true)

const items = ref([{message: 'Daisy' }, {message: 'Huggy'}, {message: 'Ollie'}])

</script>

<template>
    <div>
        <h1>v-if example</h1>
        <button @click="sheep = !sheep">Sheep?</button>
            <h2 v-if="sheep">SHEEP!</h2>
            <br>

        <h1>v-if with v-else example</h1>
        <button @click="happy = !happy">Toggle Me!</button>
            <h2 v-if="happy">Wow, you're happy!</h2>
            <h2 v-else>Oh well... I guess you're sad.</h2>
            <br>

        <h1> v-show example</h1>
        <button @click="seek = !seek">Toggle Me Too!</button> 
            <h2 v-show="seek">Where are you?</h2>
            <h2 v-show="!seek">There you are!</h2>
        <br>

        <h1> v-for example</h1>
        <li v-for="item in items">
            {{ item.message }}
        </li>
        <br>

        <h1> v-for with v-if example</h1>
        <button @click="pets = !pets">Toggle Pets!</button>
            <h2 v-if="pets"><li v-for="item in items">
            {{ item.message }}
        </li></h2>
        <br>

        <h1> v-model examples </h1>
        <p>Who is your main: {{ message }}</p>
        <input v-model="message" placeholder="edit me" />
        <br><br>

        <input type="checkbox" id="checkbox" v-model="checked" />
        <label for="checkbox">{{ checked }}</label>

    </div>
</template>

