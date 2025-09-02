<script setup>
import {onMounted, ref} from 'vue'
import TankCard from '../vue_components/TankCard.vue'
import TankEdit from '../vue_components/TankEdit.vue'
import axios from 'axios'
import { server } from 'typescript'
let server_data = ref([])
async function getTanks(){
  await fetch('http://localhost:3434/api/tanks/').then(function(response){
    return response.json()
  }).then((data) => {
      server_data.value = data
  }).catch((err) =>{
    console.log("Error: " + err)
  })
}

function showAddTanks(){
  console.log("show modal ran")
    let element = document.getElementById("add-modal")
    element.style.opacity = "100%";
    element.style.top ="20%"
    
}
onMounted(() =>{
  getTanks()
})

</script>
<template>
  <div class = "centered-flex-container">
    
    <h1>Tanks</h1>
    <button  class = "drop-shadow green" @click="showAddTanks()">Add Tank</button>

   
  
  </div>

  <div class = "grid-container">
    <TankCard v-for="(tank, index) in server_data" 
              :key="index" 
              :item="tank"
              v-if="!loading"/>
  </div>

  <TankEdit id = "add-modal"/>
  
    
</template>

