<script setup>

function closeModal(){
    let element = document.getElementById("add-modal")
    element.style.top = "-100%";
    element.style.opacity = "0%";
}
</script>


<template class ="modal-template">
    <div class ='edit-modal flex-column'>
        <h2>Tank Edit</h2>
        <label>Nation</label>
   
        <input type="text">
        <label>Name</label>
        <input type="text">
        <label>Caliber</label>
        <input type="text">
        <label>Speed</label>
        <input type="text">
        <label>Dispersion</label>
        <input type="text">
        <div class = flex-row>
            <button class= "green">Confirm</button>
            <button class = "red" @click = "closeModal()">Cancel</button>
        </div>
    </div>
    

</template>