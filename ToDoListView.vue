<script setup>
import {ref} from 'vue'

const itemID = ref(0)
const item = ref('')
const itemList = ref([])
const check = ref(false)

function addItem() {
  itemList.value.push({
    id: itemID.value++,
    newItem: item.value,
    status: check.value
  })
}

function removeItem(itemtoremove) {
  itemList.value = itemList.value.filter(xx => xx.id !== itemtoremove.id)
}

</script>

<template>
  <div class="about">
    <h1>To do list  -></h1>
    <input type="text" v-model="item">
    <button class='addbutton' @click=addItem> Add to list </button>
  
    <ol>
      <li v-for="i in itemList" :key="i.id">
        {{ i.newItem }}
        <button class='removebutton' @click=removeItem(i)> Completed </button>
      </li>
    </ol>

  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

.addbutton {
  transition-duration: 0.3s;
  background-color: white;
  color: green;
}
.addbutton:hover {
  background-color:green;
  color:white;
}

.removebutton {
  transition-duration: 0.3s;
  background-color: white;
  color: red;
}
.removebutton:hover {
  transition-duration: 0.3s;
  background-color: red;
  color: white;
}

</style>
